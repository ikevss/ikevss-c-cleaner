## ikevss C盘清理

<p align="center">
  🧹 专为 Windows AI 产品用户设计的磁盘空间分析工具 — 帮你找出 C 盘满了的原因，一键安全清理
</p>

---

### 📦 快速开始

**前提条件：**
1. 已安装 [Python 3.10+](https://www.python.org/downloads/)
2. 在 AI 助手（如 Claude Code）中安装了此 skill

**使用方法：**
在你的对话中对 AI 助手说：
```
帮我清理一下 C 盘
或
C 盘满了，分析一下哪里占了空间
```

AI 助手会自动运行扫描，生成分析报告并在浏览器中打开交互式网页报告。**全程只读，不会删你的文件**。

---

### 🛡️ 为什么选择 ikevss C盘清理？

| 特性 | 说明 |
|------|------|
| **全盲点覆盖** | 比原版多覆盖 Installer/ProgramData/回收站等系统盲区（约65GB空间） |
| **三灯分级** | 🟢可自动清 / 🟡需判断 / 🔴建议卸载 — 每个项都有明确的处置建议 |
| **七层安全校验** | Content-Length → Host → JSON → Token → 白名单 → 路径 → 根目录 |
| **随时可撤销** | 默认移入回收站，误删了也能找回来 |
| **纯标准库** | 无需 pip install，Python 3.10+ 自带所有依赖 |

---

### ⚠️ 安全警示（请阅读）

> **这是只读工具！** 在安装和扫描过程中，它**只会查看**你的磁盘使用情况，**永远不会主动删除任何文件**。  
> 你看到的每一个"删除"按钮，都必须由你**亲自点击确认**才会执行。  
> 如果你不确定某项能不能删，可以先选"只读分析"模式，让AI告诉你这个文件夹是干什么的再决定。

---

### 🔧 技术细节（给开发者）

#### 项目结构

```
ikevss-c-cleaner/
├── SKILL.md                 # Skill 定义文档（完整流程、约束规则、异常处理）
├── README.md                # 本文档（用户手册）
├── _meta.json               # 技能元数据（slug/version/publisher）
├── scripts/
│   ├── scan.py              # 只读扫描器（384行，14个函数，输出JSON）
│   ├── build_report.py      # 报告生成器（将JSON注入HTML模板）
│   └── server.py            # HTTP本地服务（7层安全校验，支持一键删除）
├── assets/
│   └── report_template.html # 交互式HTML报告前端（962行）
└── references/
    ├── index.md             # 参考文档导航
    └── windows.md           # Windows目录布局与分级指南
```

#### 命令行用法

```bash
# 完整扫描（输出JSON到标准输出）
python scripts/scan.py

# 快速模式 - 只看一级目录（约0.3秒）
python scripts/scan.py --quick

# 缓存模式 - 如果最近扫描过，直接从缓存读取（24小时有效）
python scripts/scan.py --cache

# 生成静态HTML报告
python scripts/build_report.py analysis.json output.html

# 启动本地HTTP服务（带一键删除功能）
python scripts/server.py analysis.json --no-browser  # --no-browser:不自动打开浏览器
```

#### 环境要求

- Python 3.10+
- Windows 10 / 11
- 无任何第三方依赖（全部使用标准库）

#### GitHub Pages

部署到 [GitHub Pages](https://ikevss.github.io/ikevss-c-cleaner/)，在线预览交互式报告效果。

---

### 💡 贡献与扩展

本 skill 基于原始 storage-analyzer 完全重构，专注于 Windows 平台并强化了以下几个关键能力：

- **新增 5 组系统盲区扫描**：Installer(~10-30GB)、ProgramData(~4-10GB)、回收站(~1-5GB)、Windows Temp、SoftwareDistribution
- **新增开发缓存 12 种类型**：pip、npm、cargo、gradle、maven、nuget、yarn、pnpm、playwright、go-build、uv-cache 等
- **增加确认门机制**：AI 完成分级后会停下来，向你展示 Top 5 摘要和三灯汇总，经你确认后才生成报告
- **实现七个安全检查层**：防止任何远程服务器或恶意脚本访问你的文件系统

如果你想为这个项目做贡献，可以：
1. 添加新的扫描目标（例如某个特定应用的缓存目录）
2. 增强对更多编程语言的缓存识别
3. 改进报告的样式（遵循 Design Rule：禁止圆角+单侧边框组合）
4. 添加更多语言翻译（目前支持中文，可以扩展到英文、日文等）

---

### 📝 License

MIT License © 2026 ikevss — 自由使用、修改和分发。

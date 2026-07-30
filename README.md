# ikevss C盘清理

> 🧹 ikevss 系列工具 · C 盘智能清理

纯 Windows 只读存储分析助手 — 扫描 12+ 组目标，三灯分级，交互式 HTML 报告 + 本地服务一键清理。

## 能做什么

- **只读扫描** — 全程不写不改不删，仅用 `os.scandir` / `shutil.disk_usage`
- **12 组扫描目标** — 覆盖用户目录、AppData、下载、Program Files、系统盲区（Installer / ProgramData / WinSxS / 回收站）、开发缓存等
- **三灯分级** — 🟢 可自动清理 / 🟡 需人工判断 / 🔴 建议卸载，每项带处置方案
- **交互式 HTML 报告** — 可折叠卡片、一键复制命令、平滑导航
- **本地 HTTP 服务** — 启动后可一键移废纸篓或永久删除（七层安全校验）
- **零依赖** — 纯 Python 标准库，无需 pip install

## 适用场景

**触发词**：C盘满了、磁盘满了、空间不够、清理C盘、清理空间、存储分析、磁盘分析、占空间、storage analysis、disk cleanup 等。

**不触发**：RAM/内存占用相关请求（那是运行内存，不是磁盘存储）。

## 快速开始

1. 对 AI 助手说出触发词（如 "帮我分析一下 C 盘空间"）
2. AI 助手自动加载此 Skill，依次执行扫描 → 分析 → 生成报告
3. 扫描完成后，你会看到一份包含三灯分级的交互式 HTML 报告
4. 如需在线删除：在报告中启动本地服务模式，可一键移废纸篓

## 目录结构

```
ikevss-c-cleaner/
├── SKILL.md                      # Skill 定义（流程、约束、异常处理）
├── README.md                     # 本文件
├── _meta.json                    # 版本元数据
├── scripts/
│   ├── scan.py                   # 只读扫描器（12 组目标，输出 JSON）
│   ├── build_report.py           # 报告生成器（注入 HTML 模板）
│   └── server.py                 # HTTP 服务（带删除 API + 七层安全）
├── assets/
│   └── report_template.html      # 交互式 HTML 报告模板
└── references/
    ├── index.md                  # 参考文档导航
    └── windows.md                # Windows 数据布局参考（分级指南）
```

## 核心流程

```
  scan.py              Agent (AI)                server.py
  ────────             ──────────                ─────────
  Step 1-2              Step 3                   Step 4-5
  只读扫描  ──────────→  三灯分级  ──────────→  交互式报告
  12组目标              分析 + 探查              一键清理 + 摘要
```

| 步骤 | 执行者 | 操作 | 产出 |
|------|--------|------|------|
| 1-2 | `scan.py` | 扫描 12 组目标（支持 `--quick` / `--cache`） | `%TEMP%\storage_scan.json` |
| 3 | Agent | 参考 `references/windows.md` 分级指南，探查神秘大目录，写分析 | `%TEMP%\storage_analysis.json` |
| 4 | `server.py` | 启动本地 HTTP 服务，注入分析数据 | 浏览器中交互式报告 |
| 5 | Agent | 打开报告 + 文字摘要 | 浏览器预览 + 清理建议 |

## 扫描覆盖

### 用户空间
- 用户主目录、桌面、文档、图片、视频、音乐
- `%LOCALAPPDATA%` / `%APPDATA%`
- Downloads、OneDrive

### 系统盲区（合计约 65 GB 潜在空间）
- `C:\Windows\Installer`（~10-30 GB，DISM 清理）
- `C:\ProgramData`（~4-10 GB，逐项判断）
- `C:\$Recycle.Bin`（~1-5 GB，右键清空）
- `C:\Windows\Temp`、`C:\Windows\SoftwareDistribution`
- `hiberfil.sys` / `pagefile.sys` 检测（报告建议，不手删）

### 程序与开发缓存
- `Program Files` / `Program Files (x86)`
- pip Cache、npm、Yarn、pnpm、Cargo、Gradle、Maven、NuGet、Go、Playwright 等 12 种开发缓存

## 三灯分级规则

| 级别 | 含义 | 示例 |
|------|------|------|
| 🟢 绿 | 可安全自动清理 | 临时文件、Windows Update 缓存、回收站、pip/npm 缓存 |
| 🟡 黄 | 需人工判断 | Downloads 大文件、ProgramData 子目录、旧应用缓存 |
| 🔴 红 | 不能手删，建议卸载 | WinSxS、pagefile.sys、hiberfil.sys、大型已安装应用 |

## 安全设计

### 扫描阶段
- 全程只读，不创建/修改/删除任何文件
- `C:\Windows` 仅扫描 Installer / Temp / SoftwareDistribution 三个子目录

### 报告阶段（静态 HTML）
- 清理命令仅展示，不执行
- 一键复制按钮方便手动运行

### 服务阶段（server.py）
- **七层安全校验**：Content-Length → Host → JSON → Token → 白名单 → 路径 → 根目录
- 仅允许 `127.0.0.1` / `localhost` 访问
- 删除只能操作报告中已列出的路径
- 移废纸篓使用 `SHFileOperationW`（可撤销）；永久删除需显式确认

## 命令行参考

```bash
# 完整扫描（输出 JSON）
python scripts/scan.py

# 快速模式：仅一级目录，不递归
python scripts/scan.py --quick

# 缓存模式：24h 内二次扫描 <0.1s
python scripts/scan.py --cache

# 生成 HTML 报告
python scripts/build_report.py analysis.json

# 指定输出路径
python scripts/build_report.py analysis.json C:\Users\xxx\Desktop\report.html

# 启动交互式服务（可一键删除）
python scripts/server.py analysis.json

# 服务模式跳过自动打开浏览器
python scripts/server.py analysis.json --no-browser
```

## 依赖

- Python 3.10+
- Windows 10 / 11
- 零第三方包（全部 Python 标准库）

## 关于

**ikevss C盘清理** 是 ikevss 系列工具之一，专注于 Windows 平台的磁盘空间管理。

基于对社区版 storage-analyzer (by 数字生命卡兹克) 的逆向分析和质量审查后，完全重构为纯 Windows 实现。相比社区版：
- 移除全部 macOS 代码（~150 行），代码更精炼
- 新增 5 组系统盲区扫描，覆盖率从 ~35% 提升到 ~90%
- 新增快速模式、24h 缓存、七层安全校验
- 新增确认门机制，Agent 不会跳过用户审查
- 代码质量通过 92/100 分 skill-quality-checker 审查

## 版本历史

| 版本 | 日期 | 说明 |
|------|------|------|
| v1.0.0 | 2026-07-30 | ikevss 品牌首发，基于社区版完全重构 |

## 许可证

MIT License · Copyright (c) 2026 ikevss

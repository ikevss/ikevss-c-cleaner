<p align="center">
  <img src="docs/assets/illustration-1-disk-sweep.svg" width="160" alt="">
</p>

# ikevss C盘清理

> 🧹 专为 Windows AI 开发者设计的磁盘清理 Skill — 扫描 12 组目标，三灯分级，一键安全清理

<p align="center">
  <a href="https://skills.sh/ikevss/ikevss-c-cleaner"><img src="https://skills.sh/badges/ikevss/ikevss-c-cleaner.svg" alt="skills.sh"></a>
  <img src="https://img.shields.io/badge/平台-Windows_10%2F11-blue?style=flat" alt="Windows">
  <img src="https://img.shields.io/badge/依赖-零_纯标准库-green?style=flat" alt="零依赖">
  <img src="https://img.shields.io/badge/协议-MIT-lightgrey?style=flat" alt="MIT">
</p>

***

先说说你可能遇到的困惑。

你装了 Claude Code、OpenCode、Cursor 这些 AI 工具，用着用着电脑就弹窗：

> **"C 盘空间不足"**

你打开 C 盘看了一眼——几百 GB 的硬盘，只剩十几个 GB 了。你不知道空间都被谁吃了，也不敢乱删。于是你把弹窗关掉，过两天又弹出来。

**问题就在这：** 这些 AI 工具会在 C 盘悄悄产生大量缓存——npm 包、pip 下载、uv 虚拟环境、Playwright 浏览器、十几二十个 Electron 应用的更新残留…… 它们分布在 `AppData` 里的各个角落，加起来几十 GB，但你根本不知道去哪找。

这个 Skill 就是用来解决这件事的。

***

## 它是干嘛的

一个 Claude Code Skill。装好后，你对 AI 说句话，它就会：

- **扫描** 12 组目录（包括普通工具扫不到的系统盲区：Installer、ProgramData、回收站等）
- 把所有占用空间的条目分成三种颜色——🟢 可以放心清的 / 🟡 需要你想一想的 / 🔴 最好别手碰的
- 在浏览器里打开一份交互式报告，**绿色项你点一下按钮就直接清进回收站了**

全程只读扫描，删之前必须要你确认，删掉的都进回收站——反悔了随时能找回来。

***

## 三个场景，你对号入座

### 场景一：C 盘满了，不知道谁吃的

> 你对 AI 说：**"帮我清理一下 C 盘"**

它会扫描十几秒，然后打开一个网页报告。报告最上面就是一条彩色的磁盘占用条——绿色是可自动清的、黄色是得想想的、红色是别碰的。你往下翻，每一项都写着「这是什么、多大、怎么清」。

### 场景二：想清理，但怕删错东西

绿色项点一下按钮就移进回收站了，不是永久删除。黄色项它会告诉你"这里面是什么、为什么得人工判断、如果确定要清怎么清最安全"。红色项不给删除按钮，只给「在资源管理器打开」，让你走正规卸载流程。

### 场景三：报告看完了，想持续保持 C 盘干净

报告最下面有一份长期优化建议——比如开启 Windows 存储感知、定期跑 DISM 清理、把大型缓存目录指向 D 盘。你照着做就行。

***

## 安装

两种方式，任选一种。

### 发给 AI 助手自动安装

把下面这段话发给你的 AI 助手：

```
帮我在 Claude Code 中安装 ikevss-c-cleaner 这个 Skill，用这个命令：npx skills add ikevss/ikevss-c-cleaner
```

### 命令行安装

在终端执行：

```bash
npx skills add ikevss/ikevss-c-cleaner
```

或者手动 clone 整个仓库：

```bash
git clone https://github.com/ikevss/ikevss-c-cleaner.git %USERPROFILE%\.claude\skills\ikevss-c-cleaner
```

装好之后，在 Claude Code 里对 AI 说一句就行：

```
帮我清理一下 C 盘
```

它会先扫描一遍告诉你有哪些东西，然后生成一份三灯分级的报告在浏览器里打开。**你确认了它才会删。**

***

## 目录结构

```
ikevss-c-cleaner/
├── SKILL.md                      # Skill 定义（AI 看的流程文档）
├── README.md                     # 本文件（你看的）
├── _meta.json                    # 版本元数据
├── scripts/
│   ├── scan.py                   # 只读扫描器
│   ├── build_report.py           # 报告生成器
│   └── server.py                 # HTTP 服务 + 删除 API
├── assets/
│   └── report_template.html      # 交互式 HTML 报告
├── docs/
│   ├── index.html                # 官网首页
│   └── assets/                   # 官网素材（插画、图标）
└── references/
    ├── index.md                  # 参考文档导航
    └── windows.md                # Windows 目录布局参考
```

***

## 扫描覆盖

<table>
<tr><th>用户空间</th><th>系统盲区（v2.0 新增）</th><th>开发缓存</th></tr>
<tr><td valign="top">
  用户主目录<br>
  桌面 · 文档 · 图片<br>
  AppData (Local/Roaming)<br>
  Downloads · OneDrive<br>
  .cache · .npm · .cargo<br>
  .codex · .claude · .cursor
</td><td valign="top">
  C:\Windows\Installer<br>
  C:\ProgramData<br>
  C:\$Recycle.Bin<br>
  C:\Windows\Temp<br>
  C:\Windows\SoftwareDistribution<br>
  hiberfil.sys / pagefile.sys 检测
</td><td valign="top">
  pip Cache · npm · Yarn · pnpm<br>
  Cargo · Gradle · Maven · NuGet<br>
  Go build · Playwright<br>
  uv Cache · .cache · .npm
</td></tr>
</table>

对比社区版 coverage 从 ~35% 提升到 ~90%。

***

## 安全设计

| 阶段 | 机制 |
|------|------|
| 扫描 | 全程只读，不创建/修改/删除任何文件。`C:\Windows` 仅扫描 Installer / Temp / SoftwareDistribution |
| 报告 | 清理命令仅展示不执行，可一键复制到终端手动运行 |
| 删除 | 默认「移到回收站」（可撤销）；永久删除需显式确认 |
| 服务 | **七层安全校验**：Content-Length → Host → JSON → Token → 白名单 → 路径 → 根目录。仅绑 `127.0.0.1`，外部不可达 |

***

## 常见问题

**Q：它会偷偷删我的东西吗？**
不会。扫描阶段完全不写不改不删。删除前一定先给你看分级结果、等你确认。而且默认是移到回收站，可以撤销。

**Q：我不懂命令行，能用吗？**
可以。你只需要说「帮我清理 C 盘」，然后照着网页报告上的绿色按钮点就行。所有操作都有中文说明。

**Q：为什么有些项是黄色的，不能直接清？**
因为那些目录里可能有你的聊天记录、工作文档或设计文件——只有你自己知道哪些重要。工具会告诉你里面是什么、怎么清最安全，把决定权留给你。

**Q：装了之后每次都要手动触发吗？**
对，它是一个按需使用的工具。你说触发词它才工作，不占后台资源。

***

## 许可证

MIT License · Copyright © 2026 ikevss

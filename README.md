# ikevss C盘清理

<p align="center">
  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 480 120" width="480" height="120" role="img" aria-label="ikevss C盘清理">
    <rect width="480" height="120" rx="16" fill="#f8f9fa"/>
    <!-- 磁盘图标 -->
    <g transform="translate(60,60)">
      <circle r="45" fill="none" stroke="#1a1a2e" stroke-width="3"/>
      <circle r="18" fill="#1a1a2e"/>
      <path d="M0-45 A45 45 0 0 1 38 23" fill="none" stroke="#059669" stroke-width="8" stroke-linecap="round"/>
    </g>
    <!-- 扫帚图标 -->
    <g transform="translate(170,60)">
      <line x1="0" y1="-20" x2="0" y2="25" stroke="#1a1a2e" stroke-width="4" stroke-linecap="round"/>
      <path d="M-18,20 L0,-5 L18,20" fill="none" stroke="#1a1a2e" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
      <line x1="-22" y1="28" x2="22" y2="28" stroke="#d97706" stroke-width="3" stroke-linecap="round"/>
      <line x1="-26" y1="34" x2="26" y2="34" stroke="#059669" stroke-width="3" stroke-linecap="round"/>
      <line x1="-24" y1="40" x2="24" y2="40" stroke="#dc2626" stroke-width="3" stroke-linecap="round"/>
    </g>
    <text x="250" y="55" font-family="system-ui,sans-serif" font-size="26" font-weight="700" fill="#1a1a2e">ikevss</text>
    <text x="250" y="80" font-family="system-ui,sans-serif" font-size="16" fill="#6b7280">C 盘清理 · 智能存储分析</text>
  </svg>
</p>

> 🧹 纯 Windows 只读存储分析 · 扫描 12 组目标 · 三灯分级 · 交互式 HTML 报告 · 一键安全清理 · 零依赖

---

## 工作原理

<p align="center">
  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 820 200" width="820" height="200" role="img" aria-label="5步工作流程">
    <defs>
      <marker id="arrow" markerWidth="8" markerHeight="6" refX="8" refY="3" orient="auto">
        <path d="M0,0 L8,3 L0,6 Z" fill="#d1d5db"/>
      </marker>
      <linearGradient id="grad-green" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#059669"/><stop offset="1" stop-color="#047857"/></linearGradient>
      <linearGradient id="grad-amber" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#d97706"/><stop offset="1" stop-color="#b45309"/></linearGradient>
      <linearGradient id="grad-blue" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#2563eb"/><stop offset="1" stop-color="#1d4ed8"/></linearGradient>
    </defs>
    <!-- Step 1 -->
    <rect x="10" y="60" width="130" height="80" rx="10" fill="#f0fdf4" stroke="#059669" stroke-width="1.5"/>
    <text x="75" y="88" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" font-weight="600" fill="#059669">Step 1-2</text>
    <text x="75" y="108" text-anchor="middle" font-family="system-ui,sans-serif" font-size="13" font-weight="600" fill="#1a1a2e">只读扫描</text>
    <text x="75" y="126" text-anchor="middle" font-family="monospace" font-size="10" fill="#6b7280">scan.py</text>
    <!-- arrow -->
    <line x1="142" y1="100" x2="170" y2="100" stroke="#d1d5db" stroke-width="2" marker-end="url(#arrow)"/>
    <!-- Step 2 -->
    <rect x="175" y="60" width="130" height="80" rx="10" fill="#fffbeb" stroke="#d97706" stroke-width="1.5"/>
    <text x="240" y="88" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" font-weight="600" fill="#d97706">Step 3</text>
    <text x="240" y="108" text-anchor="middle" font-family="system-ui,sans-serif" font-size="13" font-weight="600" fill="#1a1a2e">三灯分级</text>
    <text x="240" y="126" text-anchor="middle" font-family="monospace" font-size="10" fill="#6b7280">AI Agent</text>
    <!-- arrow -->
    <line x1="307" y1="100" x2="335" y2="100" stroke="#d1d5db" stroke-width="2" marker-end="url(#arrow)"/>
    <!-- Step 3 -->
    <rect x="340" y="60" width="130" height="80" rx="10" fill="#eff6ff" stroke="#2563eb" stroke-width="1.5"/>
    <text x="405" y="88" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" font-weight="600" fill="#2563eb">Step 4</text>
    <text x="405" y="108" text-anchor="middle" font-family="system-ui,sans-serif" font-size="13" font-weight="600" fill="#1a1a2e">交互式报告</text>
    <text x="405" y="126" text-anchor="middle" font-family="monospace" font-size="10" fill="#6b7280">server.py</text>
    <!-- arrow -->
    <line x1="472" y1="100" x2="500" y2="100" stroke="#d1d5db" stroke-width="2" marker-end="url(#arrow)"/>
    <!-- Step 4 -->
    <rect x="505" y="60" width="130" height="80" rx="10" fill="#f3f4f6" stroke="#6b7280" stroke-width="1.5"/>
    <text x="570" y="88" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" font-weight="600" fill="#6b7280">Step 5</text>
    <text x="570" y="108" text-anchor="middle" font-family="system-ui,sans-serif" font-size="13" font-weight="600" fill="#1a1a2e">一键清理</text>
    <text x="570" y="126" text-anchor="middle" font-family="monospace" font-size="10" fill="#6b7280">浏览器</text>
    <!-- arrow -->
    <line x1="637" y1="100" x2="670" y2="100" stroke="#d1d5db" stroke-width="2" marker-end="url(#arrow)"/>
    <!-- Result -->
    <rect x="675" y="60" width="130" height="80" rx="10" fill="#ecfdf5" stroke="#059669" stroke-width="2"/>
    <text x="740" y="98" text-anchor="middle" font-family="system-ui,sans-serif" font-size="14" font-weight="700" fill="#059669">✓ 释放空间</text>
    <text x="740" y="118" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" fill="#047857">约 XX GB</text>
    <!-- 时间标注 -->
    <text x="75" y="165" text-anchor="middle" font-family="system-ui,sans-serif" font-size="10" fill="#9ca3af">0.3s quick</text>
    <text x="240" y="165" text-anchor="middle" font-family="system-ui,sans-serif" font-size="10" fill="#9ca3af">人工审查</text>
    <text x="405" y="165" text-anchor="middle" font-family="system-ui,sans-serif" font-size="10" fill="#9ca3af">本地服务</text>
    <text x="570" y="165" text-anchor="middle" font-family="system-ui,sans-serif" font-size="10" fill="#9ca3af">确认门</text>
    <text x="740" y="165" text-anchor="middle" font-family="system-ui,sans-serif" font-size="10" fill="#9ca3af">清理完成</text>
  </svg>
</p>

## 能做什么

```
  只读扫描              三灯分级              一键清理
  ─────────            ─────────            ─────────
  os.scandir 遍历       🟢 可自动清理         移到废纸篓（可逆）
  shutil.disk_usage     🟡 需人工判断         直接删除（显式确认）
  12 组扫描目标         🔴 建议卸载           在资源管理器打开
  零文件修改            每项带处置方案          七层安全校验
```

- **只读扫描** — 全程不写不改不删，仅用 `os.scandir` / `shutil.disk_usage`
- **12 组扫描目标** — 覆盖用户目录、AppData、下载、Program Files、系统盲区（Installer / ProgramData / WinSxS / 回收站）、开发缓存等
- **三灯分级** — 🟢 可自动清理 / 🟡 需人工判断 / 🔴 建议卸载，每项带处置方案
- **交互式 HTML 报告** — 可折叠卡片、一键复制命令、锚点导航、全部展开/折叠
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

## 扫描覆盖

<p align="center">
  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 720 180" width="720" height="180" role="img" aria-label="扫描覆盖可视化">
    <!-- 用户空间 -->
    <rect x="10" y="10" width="220" height="160" rx="10" fill="#eff6ff" stroke="#93c5fd" stroke-width="1"/>
    <text x="120" y="36" text-anchor="middle" font-family="system-ui,sans-serif" font-size="13" font-weight="600" fill="#1e40af">用户空间</text>
    <text x="120" y="56" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">用户主目录 · 桌面 · 文档</text>
    <text x="120" y="74" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">AppData · Downloads · OneDrive</text>
    <text x="120" y="96" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">.cache · .npm · .cargo · .rustup</text>
    <text x="120" y="118" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">.codex · .claude · .cursor · .vscode</text>
    <text x="120" y="140" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">node_modules · pipx · .local</text>
    <!-- 系统盲区 -->
    <rect x="250" y="10" width="220" height="160" rx="10" fill="#fef2f2" stroke="#fca5a5" stroke-width="1"/>
    <text x="360" y="36" text-anchor="middle" font-family="system-ui,sans-serif" font-size="13" font-weight="600" fill="#991b1b">系统盲区 v2.0 新增</text>
    <text x="360" y="56" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">C:\Windows\Installer（~10-30 GB）</text>
    <text x="360" y="74" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">C:\ProgramData（~4-10 GB）</text>
    <text x="360" y="96" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">C:\$Recycle.Bin（~1-5 GB）</text>
    <text x="360" y="118" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">C:\Windows\Temp</text>
    <text x="360" y="140" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">hiberfil.sys / pagefile.sys 检测</text>
    <!-- 程序与开发缓存 -->
    <rect x="490" y="10" width="220" height="160" rx="10" fill="#ecfdf5" stroke="#6ee7b7" stroke-width="1"/>
    <text x="600" y="36" text-anchor="middle" font-family="system-ui,sans-serif" font-size="13" font-weight="600" fill="#065f46">程序与缓存</text>
    <text x="600" y="56" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">Program Files / (x86)</text>
    <text x="600" y="74" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">pip Cache · npm · Yarn · pnpm</text>
    <text x="600" y="96" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">Cargo · Gradle · Maven · NuGet</text>
    <text x="600" y="118" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">Go build · Playwright · uv Cache</text>
    <text x="600" y="140" text-anchor="middle" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">覆盖率 ≈90%（vs 社区版 ≈35%）</text>
  </svg>
</p>

## 三灯分级规则

<p align="center">
  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 720 100" width="720" height="100" role="img" aria-label="三灯分级">
    <!-- 绿灯 -->
    <rect x="10" y="0" width="226" height="100" rx="8" fill="#ecfdf5" stroke="#059669" stroke-width="1.5"/>
    <circle cx="50" cy="50" r="14" fill="#059669"/>
    <text x="50" y="55" text-anchor="middle" font-family="system-ui,sans-serif" font-size="14" font-weight="700" fill="#fff">✓</text>
    <text x="75" y="38" font-family="system-ui,sans-serif" font-size="15" font-weight="700" fill="#059669">可自动清理</text>
    <text x="75" y="56" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">零风险即刻释放</text>
    <text x="75" y="74" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">例：浏览器缓存 · updater残留</text>
    <text x="75" y="90" font-family="system-ui,sans-serif" font-size="10" fill="#9ca3af">废纸篓（可逆）/ 永久删除</text>
    <!-- 黄灯 -->
    <rect x="247" y="0" width="226" height="100" rx="8" fill="#fffbeb" stroke="#d97706" stroke-width="1.5"/>
    <polygon points="50,32 64,60 36,60" fill="#d97706"/>
    <text x="50" y="58" text-anchor="middle" font-family="system-ui,sans-serif" font-size="12" font-weight="700" fill="#fff">!</text>
    <text x="75" y="38" font-family="system-ui,sans-serif" font-size="15" font-weight="700" fill="#d97706">需人工判断</text>
    <text x="75" y="56" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">逐项评估后处理</text>
    <text x="75" y="74" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">例：WPS数据 · 腾讯聊天文件</text>
    <text x="75" y="90" font-family="system-ui,sans-serif" font-size="10" fill="#9ca3af">App内清理 / 安全子路径删</text>
    <!-- 红灯 -->
    <rect x="484" y="0" width="226" height="100" rx="8" fill="#fef2f2" stroke="#dc2626" stroke-width="1.5"/>
    <rect x="36" y="36" width="28" height="28" rx="4" fill="#dc2626"/>
    <text x="50" y="56" text-anchor="middle" font-family="system-ui,sans-serif" font-size="14" font-weight="700" fill="#fff">×</text>
    <text x="75" y="38" font-family="system-ui,sans-serif" font-size="15" font-weight="700" fill="#dc2626">建议卸载</text>
    <text x="75" y="56" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">走正规卸载流程，别手删</text>
    <text x="75" y="74" font-family="system-ui,sans-serif" font-size="11" fill="#6b7280">例：不再用的大应用 · 未知程序</text>
    <text x="75" y="90" font-family="system-ui,sans-serif" font-size="10" fill="#9ca3af">设置→应用→卸载</text>
  </svg>
</p>

## 安全设计

<p align="center">
  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 720 64" width="720" height="64" role="img" aria-label="七层安全校验">
    <rect x="10" y="0" width="700" height="64" rx="8" fill="#1a1a2e"/>
    <text x="360" y="20" text-anchor="middle" font-family="system-ui,sans-serif" font-size="10" fill="#6b7280">安全校验层</text>
    <!-- 层 -->
    <g transform="translate(16,30)">
      <rect x="0" y="0" width="88" height="24" rx="4" fill="#1e293b" stroke="#334155" stroke-width="1"/>
      <text x="44" y="16" text-anchor="middle" font-family="system-ui,sans-serif" font-size="9" fill="#cbd5e1">L1 · Content-Length</text>
    </g>
    <text x="108" y="47" font-family="system-ui,sans-serif" font-size="14" fill="#475569">→</text>
    <g transform="translate(120,30)">
      <rect x="0" y="0" width="68" height="24" rx="4" fill="#1e293b" stroke="#334155" stroke-width="1"/>
      <text x="34" y="16" text-anchor="middle" font-family="system-ui,sans-serif" font-size="9" fill="#cbd5e1">L2 · Host</text>
    </g>
    <text x="192" y="47" font-family="system-ui,sans-serif" font-size="14" fill="#475569">→</text>
    <g transform="translate(204,30)">
      <rect x="0" y="0" width="72" height="24" rx="4" fill="#1e293b" stroke="#334155" stroke-width="1"/>
      <text x="36" y="16" text-anchor="middle" font-family="system-ui,sans-serif" font-size="9" fill="#cbd5e1">L3 · JSON</text>
    </g>
    <text x="280" y="47" font-family="system-ui,sans-serif" font-size="14" fill="#475569">→</text>
    <g transform="translate(292,30)">
      <rect x="0" y="0" width="80" height="24" rx="4" fill="#1e293b" stroke="#334155" stroke-width="1"/>
      <text x="40" y="16" text-anchor="middle" font-family="system-ui,sans-serif" font-size="9" fill="#cbd5e1">L4 · Token</text>
    </g>
    <text x="376" y="47" font-family="system-ui,sans-serif" font-size="14" fill="#475569">→</text>
    <g transform="translate(388,30)">
      <rect x="0" y="0" width="83" height="24" rx="4" fill="#1e293b" stroke="#334155" stroke-width="1"/>
      <text x="41" y="16" text-anchor="middle" font-family="system-ui,sans-serif" font-size="9" fill="#cbd5e1">L5 · 白名单</text>
    </g>
    <text x="475" y="47" font-family="system-ui,sans-serif" font-size="14" fill="#475569">→</text>
    <g transform="translate(487,30)">
      <rect x="0" y="0" width="72" height="24" rx="4" fill="#1e293b" stroke="#334155" stroke-width="1"/>
      <text x="36" y="16" text-anchor="middle" font-family="system-ui,sans-serif" font-size="9" fill="#cbd5e1">L6 · 路径</text>
    </g>
    <text x="563" y="47" font-family="system-ui,sans-serif" font-size="14" fill="#475569">→</text>
    <g transform="translate(575,30)">
      <rect x="0" y="0" width="80" height="24" rx="4" fill="#059669" stroke="#047857" stroke-width="1"/>
      <text x="40" y="16" text-anchor="middle" font-family="system-ui,sans-serif" font-size="9" font-weight="600" fill="#fff">L7 · 根目录</text>
    </g>
  </svg>
</p>

| 阶段 | 机制 | 说明 |
|------|------|------|
| 扫描 | 全程只读 | `os.scandir` + `shutil.disk_usage`，不创建/修改/删除任何文件 |
| 扫描 | 系统目录保护 | `C:\Windows` 仅扫描 Installer/Temp/SoftwareDistribution |
| 报告 | 命令仅展示 | 静态报告中的清理命令只展示不执行，一键复制手动运行 |
| 服务 | 七层校验 | 每层独立验证，单层失败即拒绝（见上图） |
| 服务 | 仅本机可访问 | 绑定 `127.0.0.1`，外部网络无法连接 |
| 删除 | 可逆默认 | `SHFileOperationW`+`FOF_ALLOWUNDO` 移入回收站 |
| 删除 | 永久需确认 | 直接删除选项默认隐藏，需手动勾选才可见 |

## 命令行参考

```bash
# 完整扫描（输出 JSON）
python scripts/scan.py

# 快速模式：仅一级目录，不递归（0.3s）
python scripts/scan.py --quick

# 缓存模式：24h 内二次扫描 <0.1s
python scripts/scan.py --cache

# 自定义最小报告阈值（默认 50MB）
python scripts/scan.py --min-mb 10

# 生成静态 HTML 报告
python scripts/build_report.py analysis.json

# 指定输出路径
python scripts/build_report.py analysis.json C:\Users\xxx\Desktop\report.html

# 启动交互式服务（可一键删除）
python scripts/server.py analysis.json

# 服务模式跳过自动打开浏览器
python scripts/server.py analysis.json --no-browser
```

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
│   └── report_template.html      # 交互式 HTML 报告模板（962 行）
└── references/
    ├── index.md                  # 参考文档导航
    └── windows.md                # Windows 数据布局参考（分级指南）
```

## 与社区版的差异

| 维度 | 社区版 storage-analyzer | ikevss C盘清理 |
|------|-------------------------|----------------|
| 平台 | macOS + Windows | Windows only |
| 扫描目标 | 7 组 (Win) | 12 组 + 开发缓存 12 种 |
| macOS 代码 | ~150 行 | 0 行 |
| 扫描盲区 | ~65 GB 未覆盖 | 已覆盖 |
| Quick 模式 | 无 | 0.3s |
| 24h 缓存 | 无 | 二次扫描 <0.1s |
| 健康检查 | 无 | GET /health |
| 长路径处理 | 无 | `\\?\` 前缀 |
| 安全校验 | 3 层 | 7 层 |
| 确认门 | 无 | Step 3 强制暂停 |
| 标签分类 | 3 级 | 11 种互斥标签 + 正反例 |
| 键盘可访问性 | 无 | ARIA + 焦点管理 |
| 减少动画 | 无 | prefers-reduced-motion |

## 依赖

- Python 3.10+
- Windows 10 / 11
- 零第三方包（全部 Python 标准库）

## 安装

将本目录复制到 Claude Code 的 skills 目录：

```bash
# 默认路径
C:\Users\<用户名>\.claude\skills\ikevss-c-cleaner\

# 或通过 Git
git clone <repo-url> C:\Users\<用户名>\.claude\skills\ikevss-c-cleaner\
```

安装后 AI 助手会自动识别，说出"帮我分析 C 盘空间"即可触发。

## 版本历史

| 版本 | 日期 | 说明 |
|------|------|------|
| v1.1.0 | 2026-07-30 | 交互设计精炼：视觉做减法、布局居中、键盘可访问性、弃用API替换 |
| v1.0.0 | 2026-07-30 | ikevss 品牌首发，基于社区版完全重构 |

## 许可证

MIT License · Copyright (c) 2026 ikevss

# 参考文档导航

本目录包含 Windows C 盘清理技能所需的参考文档。

## 文档列表

### [windows.md](windows.md) — Windows 数据布局与分级参考

Windows 系统目录结构、文件分类规则和清理决策指南。Agent 在执行 Step 3（分析与分级）时必须阅读此文档。

**覆盖内容**：
- 多盘符策略（聚焦系统盘 C:）
- 用户目录（AppData / Temp / 浏览器缓存 / Downloads）
- 应用本体（Program Files 系列）
- 系统级目录（Installer / ProgramData / 回收站 / Temp / SoftwareDistribution / WinSxS）
- ProgramData 子目录指南（Comms / Package Cache / Autodesk / SogouInput 等）
- 开发缓存（pip / npm / Cargo / Gradle / Maven / NuGet / Go / Playwright 等 12 种）
- 系统占用（hiberfil.sys / pagefile.sys / WinSxS）
- 更新器缓存模式
- 删除机制说明

## 阅读顺序

1. **Agent 在 Step 3 开始时**：通读 [windows.md](windows.md) 全文
2. **遇到 ProgramData 大目录时**：查阅 windows.md § ProgramData 子目录指南
3. **遇到不明开发缓存时**：查阅 windows.md § 开发缓存
4. **遇到系统级目录时**：查阅 windows.md § 系统级目录

## 相关文档

- [SKILL.md](../SKILL.md) — 完整的技能定义、执行流程、附录和 FAQ
- [README.md](../README.md) — 用户手册（功能概述、快速开始、命令行参考）

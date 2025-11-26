# Android 知识笔记

这是一个用于存放 Android 开发相关知识点的笔记仓库。

## 📚 关于本仓库

本仓库用于存储使用思源笔记编写的Android开发相关笔记内容。

## 🔄 同步说明

本仓库内容通过思源笔记自动同步。详细的使用说明请查看 [同步指南](SYNC_GUIDE.md)。

### 两种同步方案

#### 方案A：导出Markdown文件后同步（⭐推荐）

1. 在思源笔记中导出笔记为Markdown格式
2. 使用 `sync_exported_md.sh` 脚本同步到GitHub
3. 文件保存在仓库的 `notes/` 目录，可直接在GitHub查看

**优点：** 格式清晰、安全、易读、适合分享

#### 方案B：直接同步data目录

1. 在思源笔记的 `data` 目录下初始化Git仓库
2. 使用 `sync_notes.sh` 脚本直接同步
3. 完全自动化，但格式不易直接查看

**优点：** 完全自动化、保留完整数据

### 快速开始

**推荐使用方案A：**

1. 在思源笔记中导出笔记为Markdown到固定目录（如 `~/Documents/SiYuan-Exports`）
2. 运行同步脚本：`./sync_exported_md.sh`
3. 设置自动同步（可选）

更多详细信息请参考 [SYNC_GUIDE.md](SYNC_GUIDE.md)。



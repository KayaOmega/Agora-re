# Agora RE（修复版 2.0.0）

基于 [newo-ether/Agora](https://github.com/newo-ether/Agora) v2.0.0 的**独立修复分发版**。

> ⚠️ 本仓库为个人修复与分发用途，**不是官方仓库**。官方项目请访问 [newo-ether/Agora](https://github.com/newo-ether/Agora)。

## 为什么有这个仓库

官方 v2.0.0 存在两个已知问题（官方 CI 已修复但未发新版）：

1. **沙箱 proot 运行库缺失**（对应官方 Issue [#85](https://github.com/newo-ether/Agora/issues/85)）
   - 官方 2.0.0 的 CI 产物未运行 `build-proot.sh`，APK 缺少
     `libproot_exec.so` / `libproot_loader.so` / `libtalloc.so`，
     导致 Local Sandbox 所有命令报 `Cannot run program .../lib/arm64/libproot_exec.so: No such file or directory`。
   - 本包从 1.3.7 取回三个库并注入 2.0.0。
2. **命令窗口崩溃**：`java.lang.IllegalStateException: No local MarkdownDimens`
   （`ChatMarkdownCodeBlock` 弹窗路径），已修复。

## 安装包

| 文件 | 说明 |
|---|---|
| `releases/Agora_2.0.0_re.apk` | 修复版 APK（包名 `com.newoether.agorare`） |

- **包名**：`com.newoether.agorare`（与官方 `com.newoether.agora` 不同，**可共存安装**）
- **版本**：2.0.0（versionCode 30）
- **SHA-256**：`97913d16019d88b1851060da3d6ce52bbc55f67ef72e74d301cb318a55b39380`
- **下载**：分支 `release/2.0.0-re` 的 `releases/` 目录，或 Releases 页发布的资产

## 安装说明

1. 下载 `Agora_2.0.0_re.apk`
2. 直接安装即可（包名不同，无需卸载任何官方版本）
3. 首次使用沙箱时按提示初始化 Alpine 根文件系统

## 更新

- 官方 v2.0.0+ 新版发布后，本仓库可能归档。
- 想要最新官方功能，请关注官方仓库 Release。

## License / 致谢

MIT 协议。原始项目：[newo-ether/Agora](https://github.com/newo-ether/Agora)。
本仓库仅基于其源码重新打包与修复，保留原作者版权声明。

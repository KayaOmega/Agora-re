# Agora 2.0.0 RE（修复版）

基于 **v2.0.0** 重建的独立修复包，与官方版本共存安装。

- **包名**：`com.newoether.agorare`（已改名，可与 `com.newoether.agora` 1.3.x、`com.starxc.agora` 2.0.0 共存）
- **版本**：2.0.0 (versionCode 30)

## 修复内容

1. **沙箱 proot 运行库缺失**（对应上游 Issue #85）
   - 补回 `lib/arm64-v8a/libproot_exec.so`、`libproot_loader.so`、`libtalloc.so`
   - 官方 2.0.0 的 CI 产物未运行 `build-proot.sh`，release 包缺这三个库，
     Local Sandbox 所有命令报 `Cannot run program .../lib/arm64/libproot_exec.so: No such file or directory`
2. **命令窗口 Markdown 崩溃**：`IllegalStateException: No local MarkdownDimens`
   （`ChatMarkdownCodeBlock` 弹窗路径）已修复

## 签名说明

- 使用 2.0.0 终端修复版同一签名（证书 SHA-256: b13b581cb4aa4d44e3566ad34f3e56c2253988f64f9badab0ffdb491c7517ad5）
- 因包名不同，与官方版互不覆盖，可同时安装

## 文件校验

SHA-256: `97913d16019d88b1851060da3d6ce52bbc55f67ef72e74d301cb318a55b39380`

## License

MIT — 原始项目：https://github.com/newo-ether/Agora

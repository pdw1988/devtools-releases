# CHUJU SQL

对着表结构，出一句能跑的 SQL。Windows / macOS 本地离线桌面工具：粘贴建表语句、连 Oracle / MySQL / PostgreSQL，生成可执行 SQL，也可以在当前连接上查询、插入一行、按主键更新或删除。

这个仓库**只放安装包和更新清单**，没有源码。

## 下载（当前 1.0.0）

| | 文件 |
|---|---|
| Windows 安装包（推荐） | [CHUJU SQL_1.0.0_x64-setup.exe](./CHUJU%20SQL_1.0.0_x64-setup.exe) |
| Windows 便携版 | [CHUJU-SQL_1.0.0_portable.exe](./CHUJU-SQL_1.0.0_portable.exe) |
| macOS Apple Silicon | [CHUJU SQL_1.0.0_aarch64.dmg](./CHUJU%20SQL_1.0.0_aarch64.dmg) |

版本号以 [`latest.json`](./latest.json) 为准。发新版后文件名会变，始终下版本号最大的那几个。

- **安装包**：装完可在应用里点「检查更新」。
- **便携版**：免安装，双击就跑。不含自动更新，升级请再下新的覆盖。
- **Mac**：未做 Apple 公证。第一次打开请 **按住 Control 点图标 → 打开**（或系统设置 → 隐私与安全性 → 仍要打开）。不要双击，Gatekeeper 会拦。

需要 64 位系统。Windows 10/11 自带 WebView2 即可。连 Oracle 11g 时本机还要 64 位 Instant Client（`oci.dll` 在 PATH 或 `OCI_LIB_DIR`）；12.1+ 一般不用装客户端。

## 免费 / 专业版

安装包默认是免费版：自导表最多 8 张（两张示例不占），连库能查、不能把表结构导进缓存；多表 / 批量 / SELECT转UPDATE / 导出 DDL 能看不能一键复制。专业版解开这些上限，在应用升级卡里粘贴许可码。

## 更新日志

见 [CHANGELOG.md](./CHANGELOG.md)。

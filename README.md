# 码上 CodeNow

Java 开发者的桌面工具箱：表结构速查、造测试数据、连库查询、Redis、日志查看、接口测试、SSH 终端，一个窗口里干完。
全部在本机算，表结构、连接、密码都不出你的电脑。

## 下载最新版 v1.13.2

| 平台 | 文件 |
| --- | --- |
| Windows 安装版 | [CodeNow_1.13.2_x64-setup.exe](https://raw.githubusercontent.com/pdw1988/devtools-releases/main/CodeNow_1.13.2_x64-setup.exe) |
| Windows 免安装 | [CodeNow_1.13.2_portable.exe](https://raw.githubusercontent.com/pdw1988/devtools-releases/main/CodeNow_1.13.2_portable.exe) |
| macOS（Apple Silicon） | [CodeNow_1.13.2_aarch64.dmg](https://raw.githubusercontent.com/pdw1988/devtools-releases/main/CodeNow_1.13.2_aarch64.dmg) |

> 国内连不上 GitHub：用 [Gitee 镜像](https://gitee.com/pdwcloud/devtools-releases/releases) 下载。
> 更新：装好后应用内「检查更新」自动升级；各版本改动见 [CHANGELOG.md](CHANGELOG.md)。

## 它做什么

- **码上查**：粘建表语句、连库或扫源码导入表结构；搜表名 / 字段 / 注释（支持拼音）；按字段规则批量造 INSERT 测试数据。
- **连库查询**：Oracle（含 11g）/ MySQL / PostgreSQL / SQLite，点表就查、手写 SQL 带补全；改数据要二次确认，
  没有 WHERE 的 UPDATE / DELETE 一律拒；SQL 优化检查和「优化记录」。
- **Redis**：单机 / 哨兵 / 集群，按前缀浏览、gzip 值自动解压、大键提醒。
- **码上测**：直接扫 Spring Boot 源码出全部接口（不用写 Swagger 注解），自动造好请求体，单接口发送、导出接口文档；
  专业版能批量回归、跑前端页面测试。
- **码上运维**：日志查看（几百 MB 本机日志秒开、按 pattern 拆列过滤）；专业版能连服务器拉日志、开 SSH 终端、互传文件。
- **常用信息**：VPN / 堡垒机 / 数据库的账号地址收在一处，逐个复制，密码加密存本机。
- **小工具**：YAML / Properties / JSON 互转校验、JSON 树形查看、Cron 表达式解读。

## 免费和专业版

装好就能用，免费功能**不限量**。专业版可在应用内免费试用 7 天，之后 199 元终身。

| | 免费 | 专业版 |
|---|---|---|
| 表结构（含连库导入）、批量 INSERT、连库查询、优化记录 | ✅ | ✅ |
| Redis 单机 / 哨兵 / 集群 | ✅ | ✅ + Java 序列化对象解析、走跳板机 |
| 日志查看 | 本机文件 | + 连服务器拉日志、多份日志合并时间线 |
| SSH 终端、服务器文件互传 | — | ✅ |
| 码上测：扫接口、单接口发送、导出文档 | ✅ | ✅ |
| 码上测：批量跑用例、全自动回归、页面测试、给 AI 用的接口说明、命令行 / CI 回归 | — | ✅ |
| 常用信息、小工具 | ✅ | ✅ |

## 开源

免费部分的源码在 [pdw1988/codenow](https://github.com/pdw1988/codenow)（Apache-2.0）。
一个要存数据库密码的工具，代码公开了你才好放心装。问题和建议也可以提在那里。

## 许可

安装包与更新元数据的著作权归作者所有（见 LICENSE），软件按应用内用户许可协议授权。
开源仓库里的代码按 Apache-2.0。

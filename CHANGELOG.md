# 更新日志

## v1.2.0 —— 2026-09-02

· 我的连接右栏已保存与连库对调
  选连接在上、填密码连库在下，空态文案同步。

· 我的连接左栏独占新建表单
  去掉折叠和顶栏说明带；连库/已保存挪右栏，列表在卡内自滚。

· 我的连接左右栏对调
  已保存与右侧表单对调，空态文案同步。

· 我的SQL库左右栏对调
  搜索与新建收藏左右对调，空态文案同步。

· 侧栏缓存区只留表数和操作
  去掉 Tauri/sqlite、体积、更新时间，底栏再矮一截。

· 左侧「我的SQL库」不被底栏挡住
  生成 SQL 组最底下会被 ↻ 刷新顶出视口；独立一级并收紧导航/缓存区高度。

· 导入页左右栏等高、空态与左栏对齐
  右栏「等待建表语句」改用 Card.fill 同构，虚线区与左侧 textarea 同起止。

· 左侧菜单空滚动条（顶底钉死）
  整栏 overflow:auto + 底脚 margin-top:auto 会空出一条条。顶底钉死，中间不够高再滚（滚动条藏掉）。

· 撤回导入铺满，侧栏恢复原样
  Page fill 把左侧菜单搞出滚动条、「我的SQL库」被藏。只保留解析表默认折起。

· 左侧菜单去掉空滚动条
  整栏 overflow:auto + 底脚 margin-top:auto 会空出一条条。顶底钉住，中间不够高再滚。

· 仅导入粘贴页铺满，解析表默认折起
  只动导入→粘贴建表；左右对半吃满视口，字段表默认折叠。不改别的菜单页。

· 生成结果加上收藏
  单表 / 多表 / 批量 / SELECT转UPDATE 的 SQL 能一键进我的SQL库，同内容不重复建。

· 单表条件常开、模板默认展开，并加上条数
  条件一行两个不折起，模板进来就开着，左栏才饱满。SELECT 条数 10/20/50/100/500。

· 单表查询字段四列，条件加上 LIKE
  左栏加宽，全选按钮不再被裁。查询字段一行四个，条件一行两个。LIKE 没写通配符时自动包成 %值%。

· Oracle 分页改回 ROWNUM
  FETCH NEXT 是 12c 才有的，11g 会 ORA-00933，看起来也不像 Oracle。

· 单表 SQL：SELECT 在前，语句铺满右侧
  SELECT 排最前。查询字段和条件字段改成连库那种一行多个。条件带等于/不等于/大于等于。

· 表结构注释能看见，长度不再带 CHAR
  VARCHAR2(100 CHAR) 的 CHAR 是 Oracle 计长单位，不该出现在长度框。AI 改成自增。

· 加载一万行不再把窗口卡死
  一万行 × 很多列全进 DOM 会把窗口卡死。先出遮罩，表格只渲染视口附近。

· 查询结果行号看得见，列宽可拖
  200 列时浏览器把 # 列挤没。改成固定列宽，表头带列序号，右边拖。

· 连库查询勾列回来，底栏按钮不再被裁
  结果卡不能挪到最上面。勾列一直开着。SQL 卡限高，多字段在网格里滚。

· 勾了记住密码，重启应用还在
  Windows 改成本机加密文件，写失败会提示。不再悄悄丢掉。

· 「粘贴 ALTER」改名为「执行 ALTER」

· 测试/本地可跨天记住密码
  连接列表和 cache.db 仍没有密码。生产不记。关掉窗口明天还能连。

· 粘贴 ALTER 放到运行旁边
  中间那张卡再折着也占高度。改成 SQL 卡上的次要按钮，点开弹窗再贴。

· 更新弹窗带上这次改了什么
  以前 latest.json 常只剩「发版 vX」，用户看不见内容。未发版的 CHANGES.md 自动写进说明；弹窗里可滚动。

· 粘贴 ALTER 展开后结果网格横条没了
  右栏 overflow:auto 两轴一起开，展开的 ALTER 把栏撑宽，结果表跟着撑满，横条没了。

· 拿掉界面上的需求确认文案
  范围清单是给评审看的，不该印在连接页和确认框里。按钮和 SQL 还在，只是不再念一遍「做什么、不做什么」。

· 选表下拉可搜索
  生成页、批量、SELECT转UPDATE、多表 JOIN 不再用原生 select 翻清单。

· 连库插入一行（PRD 19.7）
  独立写命令，SQL 框仍然只读。自增列默认不写。不拿复制 INSERT 在本表执行。

· 连库勾选行按主键更新（PRD 19.4）
  独立写命令，SQL 框仍然只读。各行同一套 SET。没主键、没勾字段都不改。

· 生成页在当前连接执行（PRD 19.5）
  单表 / 批量 / SELECT转UPDATE 确认后执行。没连上或方言对不上就禁用。

· 连库勾选行按主键删除（PRD 19.3）
  独立写命令，SQL 框仍然只读。没主键、对不上列、空主键都不删。

· 连库查询写入 PRD §十九，发版 0.9.0
  Oracle / MySQL / PostgreSQL 点表即查；密码不落盘；SQL 框不跑写操作。

· 连库查询 SQL 框铺满右栏宽度

· 连库查询：SQL 在上、结果在下

· 左侧导航收成三组

· 连库工作台：左栏不再空出一截

· 连库表单：列名在输入框前面

· 连库接入 PostgreSQL（共用壳上的第三条方言）
  - 自写 postgres_* 命令，不走 plugin-sql；页面仍用共用壳

· 真页面：我的连接 + 连库进度

· 原型：未连接恢复手填表单

· 原型：连库查询先选「我的连接」

· 原型：我的连接

· 连库后收起左侧菜单给表清单让宽

· 连库 IPC 不再动态 import Tauri 包

· 连库查询独立成一级菜单和工作台
  - 导入页不再嵌「连接数据库」Seg

· 连库后只读 SQL 查询
  - 先 200 行，加载全部最多 1 万；点列头排序、结果内筛选

· 许可码改走 Rust Ed25519
  - 私钥只在 ~/.tauri/chuju-license.key；安装包只有公钥

· macOS 发版补打 .app.tar.gz

· 删掉旧 SqlGenerator，修打包 TS2322

· 文档：11g 连库要 Instant Client，不必装 PL/SQL

· 免费 / 专业版闸门
  - 自导表最多 8 张；SELECT转UPDATE / 多表 / 批量 / 导出 DDL 能看不能拷

· 连库接入 MySQL（共用壳上的第二条方言）
  - 自写 mysql_* 命令，不走 plugin-sql；页面仍用共用壳

· 连库页抽成共用壳，方言只分连接和字典
  - 接入 MySQL 写 src/lib/dbDialects/mysql.ts 并替换 DIALECTS 槽位，不要改 DbConnect.tsx

· Oracle 只读连库导入
  - 官方纯 Rust 驱动，不经过 plugin-sql；密码不落盘

· 打包增加 macOS DMG
  - Mac 上 tauri build 出 dmg；Windows 仍是 NSIS

· SELECT转UPDATE 列名大小写和列数对不上
  - 表头小写对不上大写主键时 WHERE 不再是空的

· 产品显示名改为 CHUJU SQL
  - 窗口、侧栏、安装包显示名对齐；identifier 和缓存 key 不动

· 左侧导航按使用顺序收成一级菜单
  - 日志转SQL、SELECT转UPDATE、我的SQL库仍是独立一级入口

· 批量 INSERT 主键/唯一列连号，不再走自动值
  - 散列自动值会撞 UNIQUE，语句能生成、插不进去

· SELECT转UPDATE 网格粘贴不再被 JSON 里的竖线拆碎
  - 流程实例一类带 JSON 的查询结果不再整行错位

· SELECT转UPDATE 必须先选表再粘贴
  - 有列头按列名对齐，没列头按这张表的字段顺序对齐

· 批量生成正式页拆成 INSERT / UPDATE 两页并加回导航
  - 右栏第一张是生成结果；预览默认折起

· SELECT转UPDATE 正式页按 mockup 重排并加回导航
  - 没贴时只留粘贴；贴完右栏第一张是生成结果，预览默认折起

· 批量生成原型拆成 INSERT / UPDATE 两页
  - 导航「批量生成」作分组；旧 batch-gen.html 转到 INSERT

· 多表关联切菜单再进来会刷新
  - 再点一次当前「多表关联」也当作重新进来

· 产品方言暂时去掉 SQLite
  - 旧模板若存了 sqlite 整条丢掉，避免套用时对不上

· 模板必须点「套用」按钮，点行不再套用
  - 扫一眼名字或点删除附近时，不会把当前配置冲掉

· 多表添加关联时表名不再裁成半截
  - 左表/右表分行；弹层 portal 到 body，长表名折行，表多时可筛选

· 代码块复制仍在顶上，下载和下方复制给长语句
  - 短语句不滚就能复制；正文会在框里滚时脚上再给一次复制

· 日志转SQL「复制全部纯 SQL」按钮上提示已复制
  - 反馈在按钮上，不弹角落 toast

· 日志转SQL 按语句骨架自动选 Oracle / MySQL / PostgreSQL 字面量
  - 反引号按 MySQL 拼日期；NVL/SYSDATE 按 Oracle；ILIKE/:: 按 PostgreSQL

· 日志转SQL 去掉方言切换
  - 字面量固定按 Oracle 拼；顶栏分段和「换成 Oracle / MySQL」一并拿掉

· SQL库长表名不再被裁切
  - 列表名、所属表、按表名筛选都能看见全名

· 日志转SQL 收藏后切到我的SQL库立即可见
  - 各页同时挂着不卸载，收藏只写存储的话 SQL 库仍显示挂载时读到的旧列表

· SQL库右栏按意图互斥：新建或详情，不同时出现
  - 未选中时右侧是新建；点列表后换成详情复制；卡片脚「返回新建」回到表单

· 导航各页书面用语 + 产物优先 + 表头不再挡行
  - 多表模板默认折起；日志对照表默认折起、hero 收短；SQL库右栏先详情复制

· 单表 SQL：语句类型一次只出一种，不再四种 CRUD 混成一段
  - 勾选改成分段选择：点 SELECT 结果里就只有 SELECT，复制出去不用再自己拆

· 编辑表结构弹窗一打开就炸（类型列拆装字段名对不上）
  - toRows 原先把 { base, args } 直接 spread 进行，TypePick 读的是 typeBase，

· 我的SQL库：粘贴 SQL 即识别表名
  - 所属表名跟着 SQL 走（PRD §6.4 / §6.7），手改过表名框后不再覆盖

· 导出 DDL：DEFAULT 放到 NOT NULL 前面
  - columnParts 统一成「类型 → DEFAULT/IDENTITY → NOT NULL → 注释」

· 日志转SQL 结果卡一键收藏 · 「我的SQL库」恢复进导航
  - 每张「解析结果」卡的按钮排加「⭐ 收藏」：整卡语句存成一条收藏，

· 修云端发布构建：@tauri-apps/api 补成直接依赖
  - UpdateButton.tsx 动态 import('@tauri-apps/api/app')，但 package.json 里只有

· 修导入：全引号形态的 Oracle DDL 整批报废（导出→再导入的回路是断的）
  - node-sql-parser 的 mysql 语法把

· 编辑表结构弹窗实时生成增量 DDL（ALTER TABLE）
  - 弹窗字段表格下方新增「增量 DDL」区：拿打开弹窗时的字段和当前编辑实时 diff，

· 菜单暂只留三条：导入表结构 / 查看表结构 / 日志转SQL
  - 生成SQL / SQL语句转换 / 批量生成SQL / 我的SQL库 从左侧菜单拿掉（用户要求

· 编辑表结构：类型列加常用类型下拉 · 补种子 Java 类名显式赋值
  - 类型输入框旁常驻 ▾，点开弹常用类型清单，点选即填；照旧可以手输任意类型

· 导入页「干净态」改版：初始全空 · 导入后结果留页
  - 初始态：输入框不再预填 Oracle 示例，右栏换成虚线空态占位（.empty-hero），

· Oracle 导出 DDL：主键走独立的 alter table add constraint
  - 以前主键只以内联 PRIMARY KEY (id) 写在 CREATE TABLE 体内：约束不会丢，

· 示例表名统一大写 ORDER（速查页两张订单表的根因）· 速查卡加导入日期
  - 根因：缓存按名字原文区分大小写。种子叫小写 order、Oracle 示例导进来是

· 导航重排：配置管理暂退，七页改名并按使用顺序排列
  - 配置管理从导航拿掉（功能代码保留，PAGES 数组加回条目即恢复，

· 导入页：去掉「导入之前你该知道的」，建表输入框伸到底
  - 删「导入之前你该知道的」卡：三条说明里两条已在别处出现

· 修 bug9 速查残留内置表 · bug10 表结构可删除
  - 新增 storage/builtinSeed.ts 启动同步：凭「种子时间戳 + 退役名单」清掉

· 全项目示例只留「订单 + 订单明细」
  - 种子数据、导入页两段 DDL、日志转SQL 的 5 条样例、正则测试预设里的表名统一成

> Windows 安装包（推荐）：`CHUJU SQL_1.2.0_x64-setup.exe` · 含 Oracle 11g 客户端：GitHub Release `v1.2.0` 附件 `CHUJU-SQL_1.2.0_x64-setup-oracle11g.exe`（超 100MB，不进 git） · 便携版：`CHUJU-SQL_1.2.0_portable.exe`（免安装；不含自动更新）
> macOS：`CHUJU SQL_1.2.0_aarch64.dmg`（拖进应用程序；未签名时需右键 → 打开）

## v1.1.0 —— 2026-08-31

发版 v1.1.0

> Windows 安装包（推荐）：`CHUJU SQL_1.1.0_x64-setup.exe` · 含 Oracle 11g 客户端：`CHUJU SQL_1.1.0_x64-setup-oracle11g.exe`（本次未打） · 便携版：`CHUJU-SQL_1.1.0_portable.exe`（免安装；不含自动更新）
> macOS：`CHUJU SQL_1.1.0_aarch64.dmg`（拖进应用程序；未签名时需右键 → 打开）
## v1.0.0 —— 2026-08-31

发版 v1.0.0

> Windows 安装包：`CHUJU SQL_1.0.0_x64-setup.exe` · 便携版：`CHUJU-SQL_1.0.0_portable.exe`（免安装，直接运行；不含自动更新，需手动覆盖升级）
> macOS：`CHUJU SQL_1.0.0_aarch64.dmg`（拖进应用程序；未签名时需右键 → 打开）## v0.9.0 —— 2026-08-30

发版 v0.9.0

> Windows 安装包：`CHUJU SQL_0.9.0_x64-setup.exe` · 便携版：`CHUJU-SQL_0.9.0_portable.exe`（免安装，直接运行；不含自动更新，需手动覆盖升级）
> macOS：`CHUJU SQL_0.9.0_aarch64.dmg`（拖进应用程序；未签名时需右键 → 打开）## v0.8.0 —— 2026-08-30

发版 v0.8.0

> Windows 安装包：`CHUJU SQL_0.8.0_x64-setup.exe` · 便携版：`CHUJU-SQL_0.8.0_portable.exe`（免安装，直接运行；不含自动更新，需手动覆盖升级）
> macOS：`CHUJU SQL_0.8.0_aarch64.dmg`（拖进应用程序；未签名时需右键 → 打开）## v0.6.0 —— 2026-08-28

fix: @tauri-apps/api 补成直接依赖——修云端构建 TS2307

- UpdateButton.tsx 动态 import('@tauri-apps/api/app')，但 package.json 里只有
  三个 @tauri-apps/plugin-*，api 一直是传递依赖。pnpm 严格布局不会把它链到
  项目根 node_modules，云端干净 checkout 的 tsc -b 当场报 TS2307 找不到模块
- 本地四道闸门为什么一直全绿：C:\Users\pdw\node_modules（用户主目录）里有
  一份野生的 @tauri-apps/api，TS 沿父目录找 node_modules 时捡到了，把缺依赖
  掩住了。这份野的换台机器就没有——不能当依赖用，只能当陷阱
- pnpm add @tauri-apps/api@^2.11.1：与传递依赖同版本（2.11.1），./app 走
  exports 的 ./* 通配解析到 app.d.ts；require.resolve 已落在项目自己的
  .pnpm store 里，不再经过主目录

> 便携版：`DevTools_0.6.0_portable.exe`（免安装，直接运行；不含自动更新，需手动覆盖升级）

# 更新日志
## v0.4.0 —— 2026-08-27

新增免安装包

> 便携版：`DevTools_0.4.0_portable.exe`（免安装，直接运行；不含自动更新，需手动覆盖升级）
## v0.3.0 —— 2026-08-27

新增select转update，批量生成功能

> 便携版：`DevTools_0.3.0_portable.exe`（免安装，直接运行；不含自动更新，需手动覆盖升级）## v0.2.0 —— 2026-08-26

新增配置管理页：YAML/Properties 一键互转保留注释、实时校验报行号、智能提示；内置自动更新

# 更新日志

## v0.9.0 —— 2026-08-30

发版 v0.9.0

> Windows 安装包：`CHUJU SQL_0.9.0_x64-setup.exe` · 便携版：`CHUJU-SQL_0.9.0_portable.exe`（免安装，直接运行；不含自动更新，需手动覆盖升级）
> macOS：`CHUJU SQL_0.9.0_aarch64.dmg`（拖进应用程序；未签名时需右键 → 打开）

## v0.8.0 —— 2026-08-30

发版 v0.8.0

> Windows 安装包：`CHUJU SQL_0.8.0_x64-setup.exe` · 便携版：`CHUJU-SQL_0.8.0_portable.exe`（免安装，直接运行；不含自动更新，需手动覆盖升级）
> macOS：`CHUJU SQL_0.8.0_aarch64.dmg`（拖进应用程序；未签名时需右键 → 打开）
## v0.6.0 —— 2026-08-28

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

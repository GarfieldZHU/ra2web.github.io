# 红色警戒2 · 网页版（个人自部署）

个人自部署的《红色警戒2》网页版实例，纯自用、非商业、不对外运营。

- 访问：https://garfieldzhu.github.io/ra2web.github.io/
- 用途：个人研究浏览器端 RTS 的渲染与资源加载（MIX/SHP/PCX 解析、WebAssembly、WebRTC 联机）
- 商业化：无。不投放广告、不做付费、不提供托管服务

## 版权

《Command & Conquer: Red Alert 2》及其全部美术、音频、关卡素材版权归 **Electronic Arts Inc.** 所有。
本仓库仅包含自部署所需的网页外壳与配置，不含游戏素材本体；素材由公开的游戏资源服务在运行时加载。

本项目基于开源的网页版红警移植项目二次部署，仅用于个人学习与非商业用途。

## 部署备注

- 静态站点，GitHub Pages 托管，无服务端
- 游戏资源通过 `config.ini` 中的 CDN 地址在运行时拉取，首次加载后由浏览器缓存

## 开屏图来源

网页使用 `res/custom/splash.webp`（856×736）。原始 PNG 像素源文件保存在
`res/custom/src/splash-856x736.png`，可直接追溯复现：

1. 下载 `config.ini` 中 `gameResArchiveUrl` 指向的完整资源包（`full-pack.7z`）
2. 从中取出 `RA2.MIX`
3. 在 `RA2.MIX` 内按 PCX 文件头（`0A 05 01 08`）定位，取 `856×736` 那张官方标题美术
4. 原始像素直接转为 `res/custom/src/splash-856x736.png`

网页中的 WebP 是从该 PNG 源文件编码得到的发布副本，尺寸保持 856×736；没有
inpaint、裁切、缩放或重绘。

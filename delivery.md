# 五一浙西行程网页 · 交付说明

## 正式可访问地址

- **正式 HTTPS 页面**：https://fengqve.github.io/zhexi-trip-site/
- **GitHub 仓库**：https://github.com/fengqve/zhexi-trip-site

这个地址可以直接发给老人打开，不会再出现本地文件或临时隧道类安全提示。

## 本次已完成的硬要求

### 1) 正式静态托管
- 已发布到 **GitHub Pages**
- 域名为 GitHub 官方 HTTPS 域名，浏览器正常显示安全锁
- 已实测首页返回 `200 OK`

### 2) 真实地图路径
- 页面已接入 **Leaflet + OpenStreetMap**
- 使用 **OSRM 驾车路线服务** 动态生成整条主线
- 地图中的每个落脚点都可点击，弹窗里可直接打开高德定位
- 当前主线覆盖：杭州 → 开化县城 → 霞山古村 → 钱江源国家公园 → 高田坑村 → 龙游石窟 → 桐庐县城 → 深澳古村 → 芦茨村 → 石舍村

### 3) 真实照片替换示意图
已替换为真实照片，并随站点一同部署：
- `assets/photos/kaihua-yanglin.jpg`
- `assets/photos/qianjiangyuan.jpg`
- `assets/photos/longyou-grottoes.jpg`
- `assets/photos/fuchun-river.jpg`

## 页面主要改动

- 重做为 **老人友好的大字版单页**
- 保留原有中文行程逻辑，并改成更容易扫读的每日卡片
- 增加“真实路线地图”板块，替代之前的示意路线条
- 增加“真实照片”板块，替代原来的 SVG 占位图
- 手机上优化了字号、留白、点按区域和信息层级

## 图片来源

本次使用的真实照片来源如下：

1. **开化古村方向实景**
   - 文件：`201901 Yanglin, Kaihua.jpg`
   - 来源：Wikimedia Commons
   - 用途：代表开化古村与乡村风貌段

2. **钱江源国家公园实景**
   - 文件：`Kaihua Qianjiangyuan Guojia Senlin Gongyuan 2018.07.20 07-28-19.jpg`
   - 来源：Wikimedia Commons
   - 用途：对应钱江源 / 齐溪段

3. **龙游石窟实景**
   - 文件：`Longyou Grottoes Banner.jpg`
   - 来源：Wikimedia Commons
   - 用途：对应龙游石窟段

4. **富春江 / 桐庐实景**
   - 文件：`Fuchun River.jpg`
   - 来源：Wikimedia Commons
   - 用途：对应桐庐、芦茨、富春江收尾段

## 验证记录

### 本地验证
- `python3 -m http.server 4173` 启动本地预览成功
- 本地首页返回 `HTTP/1.0 200 OK`
- 页面已包含真实照片引用、OSRM 路线请求、地图脚本

### 线上验证
- `https://fengqve.github.io/zhexi-trip-site/` 已返回 `200`
- 线上图片 `assets/photos/qianjiangyuan.jpg` 已返回 `200`
- 首页 HTML 已确认包含：
  - “真实路线地图”
  - 真实照片资源路径
  - `router.project-osrm.org` 路线请求

## 剩余限制

- 开化段目前使用的是 **开化实景代表图**，不是“霞山古村”与“高田坑村”各自一张一一对应的独立照片；但已经不再是示意图，而是真实实景照片。
- 地图坐标为人工校准后的近似落点，适合行程展示与导航跳转，不等同于景区售票口级别的精确采集。
- 地图路线依赖公开 OSRM 服务，若外部服务暂时波动，页面会自动退回到点位连线显示，不影响阅读。

## 仓库与提交

- 本目录已初始化为独立 git 仓库
- 已提交：`feat: build elderly-friendly zhexi trip site`

生成时间：2026-04-25

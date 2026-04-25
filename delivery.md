# 五一浙西行程网页 · 交付说明

## 正式可访问地址

- **正式 HTTPS 页面**：https://fengqve.github.io/zhexi-trip-site/
- **GitHub 仓库**：https://github.com/fengqve/zhexi-trip-site

这个地址可以直接发给家里人打开，不会再出现本地文件或临时隧道类安全提示。

## 本次新增完成内容

### 补充修正（2026-04-25 晚）
- 已按用户原始行程把后半段改回：**D5 龙游石窟 → 桐庐、D6 深澳—荻浦—环溪、D7 石舍—茆坪—芦茨溪谷线后返杭**。
- 首页已删除原先最前面的两张说明卡片，打开后直接进入逐日卡片。
- 路线地图保留，但已移到页面最底部。


### 1) D1-D8 每一天都单独配了真实图
这次已经把页面改成 **逐日配图**，不再用一张图笼统代表多天。

当前逐日图片为：
- `assets/photos/d1-kaihua-county.jpg`
- `assets/photos/d2-kaihua-yanglin.jpg`
- `assets/photos/d3-qianjiangyuan.jpg`
- `assets/photos/d4-qianjiangyuan-trail.jpg`
- `assets/photos/d5-longyou-county.jpg`
- `assets/photos/d6-longyou-grottoes.jpg`
- `assets/photos/d7-shenao-village.jpg`
- `assets/photos/d8-tonglu.jpg`

说明：
- D1、D2、D3、D4 已分别拆成开化到达、古村慢游、钱江源进山、长虹乡村线四种不同视觉。
- 其中 D2、D3、D6、D7 对应性较强。
- D4 的高田坑 / 台回山公开可稳定复用图片较少，因此使用了同属开化钱江源山野线的真实场景图，尽量贴近当天气质，并在页面与本说明里如实标注。
- D8 采用桐庐实景图，对应返程前的石舍 / 茆坪 / 芦茨溪谷收尾段整体感觉。

### 2) 每一天都补上了天气、穿戴建议、当天提醒
页面内 D1-D8 每张卡片都新增了：
- 当天天气概览
- 温度区间
- 降雨概率
- 穿戴建议
- 当天提醒

天气口径：
- 来源：**Open-Meteo Forecast API**
- 查询时间：**2026-04-25**
- 坐标口径：
  - 开化段使用开化县城坐标
  - 龙游段使用龙游县城 / 石窟区域坐标
  - 桐庐段使用桐庐县城坐标
- 页面中已经明确提示：**山里天气变化快，出发前请再看一眼最新预报**

本次写入页面的天气摘要如下：
- D1 开化：多云，9°C - 23°C，降雨概率约 19%
- D2 开化：多云，8°C - 26°C，降雨概率约 0%
- D3 钱江源：多云到阴，11°C - 27°C，降雨概率约 39%
- D4 高田坑 / 台回山：小雨，17°C - 19°C，降雨概率约 79%
- D5 龙游转场：小雨，17°C - 26°C，降雨概率约 77%
- D6 龙游石窟：多云，14°C - 26°C，降雨概率约 23%
- D7 桐庐古村线：多云，15°C - 29°C，降雨概率约 18%
- D8 桐庐返杭：多云偏热，15°C - 31°C，降雨概率约 14%

### 3) 开化段已经拆细
之前“开化段”容易看成一整块，现在已经拆成：
- **D1** 杭州 → 开化，纯到达适应
- **D2** 霞山古村 + 马金溪，偏人文慢游
- **D3** 钱江源 / 齐溪，偏森林溪谷
- **D4** 高田坑 + 台回山，偏小众乡村线

这样家里人打开页面时，更容易理解前四天不是一个模糊的大段，而是四天节奏明显不同。

## 页面主要改动

- 保持单页大字、手机友好排版
- 每日卡片顶部直接放当天真实图
- 每天卡片里都加入天气、穿什么、当天提醒
- “逐日实景”板块改成 8 张图快速总览
- 保留真实路线地图和高德定位跳转
- 全页继续避免使用不合适的称呼，统一用“家里人”等中性表达

## 图片来源

本次新增逐日图片来源如下：

1. **D1 开化到达日**
   - 文件：`Kaihua Qianjiangyuan Guojia Senlin Gongyuan 2018.07.22 08-51-04.jpg`
   - 站内文件：`assets/photos/d1-kaihua-county.jpg`
   - 来源：Wikimedia Commons / 开化县词条主图

2. **D2 霞山古村线**
   - 文件：`201901 Yanglin, Kaihua.jpg`
   - 站内文件：`assets/photos/d2-kaihua-yanglin.jpg`
   - 来源：Wikimedia Commons

3. **D3 钱江源 / 齐溪**
   - 文件：`Kaihua Qianjiangyuan Guojia Senlin Gongyuan 2018.07.23 08-20-56.jpg`
   - 站内文件：`assets/photos/d3-qianjiangyuan.jpg`
   - 来源：Wikimedia Commons / 钱江源国家公园词条主图

4. **D4 高田坑 / 台回山线**
   - 文件：`Kaihua Qianjiangyuan Guojia Senlin Gongyuan 2018.07.23 07-58-27.jpg`
   - 站内文件：`assets/photos/d4-qianjiangyuan-trail.jpg`
   - 来源：Wikimedia Commons
   - 说明：用于代表开化山野乡村线，当天主题贴近，但不是高田坑村口一一对应照片

5. **D5 龙游转场**
   - 文件：`20210728 龙游县城 航拍.png`
   - 站内文件：`assets/photos/d5-longyou-county.jpg`
   - 来源：Wikimedia Commons / 龙游县词条主图

6. **D6 龙游石窟**
   - 文件：`Longyou Grottoes Banner.jpg`
   - 站内文件：`assets/photos/d6-longyou-grottoes.jpg`
   - 来源：Wikimedia Commons

7. **D7 深澳古村 + 芦茨线**
   - 文件：`Gongsi Hall in Shen'ao Village 03 2016-09.jpg`
   - 站内文件：`assets/photos/d7-shenao-village.jpg`
   - 来源：Wikimedia Commons / 深澳村词条主图

8. **D8 桐庐返程日**
   - 文件：`201806 Tonglu, Hangzhou.jpg`
   - 站内文件：`assets/photos/d8-tonglu.jpg`
   - 来源：Wikimedia Commons / 桐庐县词条主图

## 验证记录

### 本地验证
- 页面 HTML 已改为逐日配图结构
- D1-D8 新图片文件已落地到 `assets/photos/`
- 每日卡片已包含天气、穿戴建议、提醒字段
- 地图脚本仍保留真实点位与路线绘制逻辑

### 上线前建议再检查一遍
- 出发前 1 天或当天早上，再更新一次天气页面截图或预报口径
- 若 D4、D5 实际雨势增强，可在页面口头转发时提醒“只留最顺的一段，不赶山路”

## 仓库与提交

- 当前目录已是独立 git 仓库
- 本次改动完成后将继续提交并推送到 GitHub Pages

生成时间：2026-04-25

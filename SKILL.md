---
name: personal-taste
description: E 的个人前端视觉品味（复古未来主义）。Use whenever building, styling, or redesigning any web frontend for E — landing pages, portfolios, personal sites, demos, posters, widgets — unless the project explicitly mandates another brand or style. Covers color, light, layout, texture, typography, imagery, and motion rules.
---

# E 的前端品味：复古未来主义

用 20 世纪的材料与手艺，表达对未来的想象。三支柱：

1. **纪念碑性**——庄重、厚重、压得住，竖向的崇高感（安藤的混凝土、Daily Planet 的高塔）
2. **模拟材料**——质感来自混凝土/油墨/网点/胶片/纸的密度，绝不来自数码光泽
3. **构建的世界**——一切元素经过设计转译（插画、剪影、单色 wash）才许入画，未经处理的"真实"不许进来

适用范围：E 的个人/视觉向项目默认全开。若是面向外部受众的正式产品，本档案降级为"默认倾向"，与受众需求冲突时向 E 提出再定。

## 0. 动手前声明（强制）

写代码前先用一句话声明：**本页氛围色 = ___（灰阶 / 夜蓝 / 血红 / Kill Bill 黄 / …），唯一发光焦点 = ___**。

## 1. 色彩：氛围色统治

- **无色优于庸色**：没有把握时归零，灰阶世界靠明暗与质感撑住高级感
- 用色 = 让**一种色相像环境光淹没整页**（BTAS 的红天）。灰阶也是氛围色的一种。禁多色相混搭，禁"主色+辅色+点缀色"式配色课作业
- 氛围之内：**黑是结构，白是光**。平涂大色块
- 敢饱和：铁律是"单一"，不是"低饱和"。无立场的安全调色（青橙、灰蒙蒙）比丑更糟
- 深色为主场；浅色档 = **裸色混凝土**（底 #D6D4CE~#CCC8BF，墨 #1B1B1D，黑仍是结构色；焦点由"发光"转为"开槽"——浅色世界里的暗缝就是光缝的反相），不用纯白底
- 禁纯黑纯白：off-black #0F0F10~#16161A，off-white #EDECE8 一族

## 2. 光：黑暗中的稀缺光源

- **全页唯一焦点 = 视觉重心**：可以是光（光缝、白窗、一轮月、一道霓虹），也可以是唯一一抹饱和色（Kill Bill 雪夜决斗：夜蓝氛围里唯一的黄战衣）。光焦点与色焦点不叠加，二选一
- 辉光（glow/box-shadow 发光）合法但稀缺：一道是光，一墙是聒噪
- 光是负空间：从黑暗里漏出来（缝隙、镂空、剪影后的天空），不是叠上去的特效

## 3. 形态与布局

- 大块面、实心、**剪影成立**：任何区块缩成剪影后轮廓依然要硬
- 直角为主，border-radius 默认 0~4px；曲线只许雕塑感大曲线（整面墙的弧、deco 流线），卡片 16px+ 大圆角即犯规
- Art Deco 语汇可用：竖向细线、阶梯形体、对称的庄重（但不甜）
- **留白即静，聒噪即廉价**：每屏一个重心，删无可删才出厂
- 拒绝三等宽卡片阵；用不对称的大小块组合
- **受限立体**：立体感只许两种来源——①喷绘式体量明暗：单一光源、单一色相的大块面渐变（Daily Planet 式，"光照在物上"）②印刷与字体工艺：铬字（含回到未来式暖金属渐变——黄→橙→红视为高温金属的明暗，**仅限金属字内部**，不许外溢成页面/按钮渐变）、凹凸压印、letterpress 阴刻、雕版线刻。**界面部件永远是平的**：禁卡片悬浮投影、neumorphism、玻璃 3D 物。单色相明暗渐变因此合法，多色相渐变仍禁

## 4. 材质

- 哑光为本。禁塑料光泽、亮闪渐变、轻薄描边；glassmorphism 默认禁用（除非 Apple 旗舰店级厚实精密且 E 点头）
- 质感库：混凝土颗粒、半调网点、胶片颗粒、纸纹油墨、贵重材质满幅特写（WATTBA 公式：单色 wash + 材质密度 = 奢侈）
- grain 配方（固定覆盖层，不随内容滚动，opacity 0.04~0.08，pointer-events:none）：

```css
.grain::after {
  content: ""; position: fixed; inset: 0; z-index: 9999;
  pointer-events: none; opacity: .06;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='160' height='160'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='2'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
}
```

- 半调网点：`background-image: radial-gradient(circle, rgba(255,255,255,.16) 1px, transparent 1px); background-size: 5px 5px;` 盖在图像/色块上
- 做旧印刷三件套（80s 变形金刚封面式，整体复古质感的来源）：①纸色 wash——暖米 #E5DCC3 做底或低透明度叠在区块上 ②双尺度网点——4px 细网 + 9px 粗网两层叠加 ③边角做旧——大半径 radial-gradient 暗角 + grain 局部加重到 0.1。可选第四件：标题加 1px 偏移、同色系低透明度重影（错位印刷感）
- 雕版线刻（钞票/铜版雕刻，Mellan 式单线成像）：细密平行线随形体起伏造体积，是"受限立体"的极致形态——CSS 用 repeating-linear-gradient 1px 细线或线刻风格 SVG 插图实现；与铜版手写字体同源，适合肖像、徽章、"印钞感"场合

## 5. 字体：两极并立

- **大声极**（默认标题，已验证）：Anton（Kill Bill 片头同气质）/ Archivo Black / Bebas Neue（60s 招牌条幅感，好莱坞往事气质）/ Ultra（Aachen 系重砸 slab，昆汀线）/ Shrikhand（70s 圆胖 groovy，Jackie Brown 气质）；中文：站酷庆科黄油体 / Noto Sans SC 900。允许全大写 + 宽字距做 deco 感
- **华丽极**（优雅场合，已验证）：铜版手写 Mrs Saint Delafield（E 票选入库）/ Pinyon Script / Snell Roundhand（macOS 自带）；冷面衬线 Bodoni Moda Italic（E 票选确认，美国精神病人名片气质）/ Didot；中文 Noto Serif SC 900 / ZCOOL XiaoWei
- **已试样落选**（两轮试衣间实测；除非 E 重新点名，不主动用）：Alfa Slab One、Rye / Smokum、Special Elite、哥特 blackletter 系（Grenze Gotisch / UnifrakturMaguntia / Pirata One）、Bowlby One、Chicle、Ewert、Permanent Marker、Rock Salt
- **开放库原则**（E 原话：字体无需定死，这只是大概结果）：以上是已验证基线，不是封闭白名单。遇到符合两极气质的新字体，先做实样给 E 过目，点头即入库
- 待试样候选：回到未来式铬斜体冲刺感（如 Faster One），出实样后再定
- 正文：克制无衬线可打工（system-ui / Archivo 400）
- **公敌：现代中性无衬线当主角**。标题必须有历史感的性格

## 6. 图像政策

- 入画资格：插画 / 素描 / 剪影图形 / 雕版线刻版画 / 重度处理的摄影（单色 wash + 颗粒或网点）。舞台感的人造场景合法——明知是布景的美（Kill Bill 雪庭）正是"构建的世界"
- **禁纪实实拍直接入画**（Views 教训）。摄影只能以"材质"身份出现（满幅纹理特写），不能以"场景记录"身份出现
- 占位图同样要处理成单色 + 网点，不用彩色 stock 照

## 7. 动效：昆汀法则

- **静为常态，动则决绝**：触发式动画 160~280ms，easing 用 `cubic-bezier(0.22,1,0.36,1)` 或 `steps()` 硬切，动完即止
- 禁持续漂浮、呼吸、无限循环、缓慢视差——漂浮感 = 动效界的廉价感
- 章节卡式硬转场合法且鼓励（满幅色块 + 大字标题，Kill Bill 章节卡）
- 每个动画一句话说不清动机就删。只动 transform/opacity。`prefers-reduced-motion` 必须实现

## 8. 工程底线

- 对比度 WCAG AA（4.5:1 起）；表单 label 在输入框上方；交互必有 hover/active/loading/empty 态
- 深浅双模式从第一行代码开始（深色是主场）
- grain/网点层永远 pointer-events:none；性能预算 LCP < 2.5s

## 9. 禁区（与 E 实测确认）

企业孟菲斯小人插画 / 紫渐变玻璃卡片 / 糖果圆角马卡龙 / 多色霓虹堆砌 / 甜粉彩气质 / 青橙安全调色 / 塑料光泽 / Inter 系中性无衬线当主角 / 纪实实拍 / 漂浮动效 / 纯黑纯白 / 三等宽卡片阵 / 一切聒噪

### 9.X 头号危险近邻：科技大屏 / 数字孪生 HUD 风（E 主动逮到的反例）

国内竞赛/政企大屏的默认模板：深蓝渐变底 + 青/橙/红/黄多色霓虹描边 + 满屏发光卡片 + 细瘦无衬线 + 发光大数字。**最危险，因为它和本品味共享深色基底，最易蒙混过关。** 三宗罪：①多色相混用破"单一" ②满屏辉光破"唯一稀缺光源" ③纯数码光泽零模拟质感。它是"用数码玻璃表达未来"，正是复古未来主义（"用模拟材料表达未来"）的对立面。

判别口诀：**本品味 = 黑暗里一道光；此反例 = 黑暗里处处是光。** 同样深底，差别只在光的稀缺性。做任何深色界面（尤其涉及数据/指标展示）时，主动自查是否正在滑向此风格。即便项目要求数据可视化，也用"单色相 + 唯一焦点 + 哑光卡片 + 有性格的标题字"重做，不套大屏模板。

## 10. 出厂检查

- [ ] 已声明氛围色与唯一发光焦点
- [ ] 全页色相 ≤ 1（灰阶不计入）
- [ ] 发光元素 ≤ 1 处
- [ ] 圆角 ≤ 4px，或属于雕塑大曲线
- [ ] 无塑料光泽 / 多色渐变 / 玻璃卡片
- [ ] 标题字体有历史感性格，正文无衬线只打工
- [ ] 所有图像经过转译（剪影/素描/单色 wash + 网点）
- [ ] 无无限循环动画；reduced-motion 已实现
- [ ] 剪影测试：把页面截图压成两阶黑白，构图依然成立
- [ ] 聒噪测试：每屏一个重心，再删一个元素就伤筋动骨

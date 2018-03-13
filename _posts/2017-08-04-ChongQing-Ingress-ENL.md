---
layout:     post
title:      ChongQing Ingress ENL进阶培训教程
date:       2017-08-04
author:     ARay
header-img: img/image10.jpg
catalog: true
tags:
- Ingress
---

因为初级教程 @BeltAndRoad 已经写过了，我就写一份进阶的教程吧。


# 游戏的辅助App

> iOS用户首先不用看这一章了，这里大部分都是Android的福利。

**Android 系统中有一些十分实用的 App 可以配合 Ingress 游戏使用:**

> **Integrated Timer for Ingress**: 记录并自动提示 Hack 的冷却时间、剩余 Hack 次数、Burnout 冷却时间等。

> **Ingress Helper**: 运行 Ingress 时保持屏幕常亮、GPS 活动。 可辅助用于 Trekker 成就的取得。

> **Ingress Portal Calc**: 可以计算一系列与 Portal 有关的参数， 如最长 Link 距离等。

> **Ingress Intel Helper**: 适配手机屏幕的移动版 Intel 地图。

> **Glyph predictor**: 在进行 Glyph hack 时辅助记忆的工具。

> **Agent Stats**:这是一个iOS和Android都有的app，用于记录和分析个人的Ingress数据。（需要自己上传游戏个人页面的数据）

> **IITC-Mobile**:这个app最好是在桌面版的Chrome上运行，手机屏幕太小了。

**请谨慎使用相关小工具，被Ban或者封号这种事情比较玄学。**

# 升级所需AP和成就牌

| 等级   | 所需AP       |  XM上限   | 充电距离上限 |
| :--- | :--------- | :-----: | -----: |
| L1   | 0AP        | 3000XM  |  250KM |
| L2   | 2500AP     | 4000XM  |  500KM |
| L3   | 20000AP    | 5000XM  |  750KM |
| L4   | 70000AP    | 6000XM  | 1000KM |
| L5   | 150000AP   | 7000XM  | 1250KM |
| L6   | 300000AP   | 8000XM  | 1500KM |
| L7   | 600000AP   | 9000XM  | 1750KM |
| L8   | 1200000AP  | 10000XM | 2000KM |
| L9   | 2400000AP  | 11500XM | 2250KM |
| L10  | 4000000AP  | 13000XM | 2500KM |
| L11  | 6000000AP  | 14500XM | 2750KM |
| L12  | 8400000AP  | 16000XM | 3000KM |
| L13  | 12000000AP | 17500XM | 3250KM |
| L14  | 17000000AP | 19000XM | 3500KM |
| L15  | 20000000AP | 20500XM | 3750KM |
| L16  | 40000000AP | 22000XM | 4000KM |

除了AP的需求之外，L9～L16还有额外的成就要求。

> 高级成就同时计入低级成就。

> 金牌=一个金牌+一个银牌+一个铜牌

| 等级   | 银牌 |  金牌   | 白金牌 | 黑牌 |
| :---: | :---------: | :-----: | :-----: | :----: |
| L9 | 4 | 1 | - | - |
| L10 | 5 | 2 | - | - |
| L11 | 6 | 4 | - | - |
| L12 | 7 | 6 | - | - |
| L13 | - | 7 | 1 | - |
| L14 | - | - | 2 | - |
| L15 | - | - | 3 | - |
| L16 | - | - | 4 | 2 |

升级的过程就不用再说了。

> L1-L8 升级带来的好处是最明显的: 升入高级后可以使用更高级的道具。 

> L9-L16 升级带来的好处相比来说没有那么直接。 充电距离上限的提升对于大部分玩家来说意义不大， 但 XM 上限的提升确实很有帮助。

下图直观地显示了 L9-L16 的需求以及带来的好处:

![][image-1]

# Portal 解析

一个 Portal 有如下指标:

**等级(Level)**

> Portal 的等级由平均 Resonator 等级决定。 

> 实际显示在 Portal 界面的等级向下取整。 比如一个玩家独自可部署的最高级 Portal， 其平均 Resonator 等级为 (8+7+6+6+5+5+4+4)/8=5.625 ， 显示为5级。 

> Level 将会影响 **Hack 得到道具的等级以及最长 Link 距离**。

**防御值(Mitigation)**

> 防御值即是 Portal 受到攻击时， 其上 Resonator 减少的伤害的百分比。 

> 比如一个 Portal 的防御值为80， 那么其上 Resonator 实际受到的伤害为防御值为零时的20%。 

**Portal 默认的防御值是零， 可以通过以下两种方式提升防御值**:

1. 部署 **Portal Shield**。 
2. **Link**。

> 当 Portal 连接有 Link 将会提升防御值。 Link 数少时对防御值的提升比较显著。 当 Link 较多时， 增长趋缓。 

| link数量 | 增加的防御值 |
|:---:|:---:|
|1|16|
|2|28|
|3|37|
|4|43|
|5|48|

> 由上表可见 2根 Link 的防御效果相当于一个 Common Shield， 3根 Link 的防御效果相当于一个 Rare Shield。 

> 其对于 Portal 防御的提升效果明显。 而且 Link 相比于 Mod 被攻击时没有被去除的几率。

> 只有当 Portal 上的 Resonator 的数量小于 3 时， 其连接的 Link 才会消失。

**需要注意的是， 防御值的上限为95， 即当根据上述法则计算得到的防御值大于95时， 防御值将被强行设置成95。**

**最长 Link 距离**

> Portal 的最长 Link 距离为 **160m×(avg(Resonator.lvl))4** 。 

比如之前已计算得到一个玩家独自可部署的最高级 Portal 其平均 Resonator 等级为5.625， 则 Link 距离为 160m×5.6254=160.18km 。 

对于同一个城市内的 Link， 这个距离通常已经足够了。

> 部署**Link Amp**可以额外增加这一数值。

**Burnout 前的 Hack 次数**

> 在 Burnout 之前， 一个 Portal 可以被 Hack 四次。

> 使用 Multi-Hack 可以额外增加这一数值。

> 两次 Hack 之间的冷却时间为 5 分钟。 使用 Heat Sink 可以减少冷却时间。 

**当 Hack 或者攻击敌方 Portal 时将会受到 Portal 的攻击。 **

> Portal 的攻击范围为 40m+(5×Portal.lvl) 

> 注意到 Scanner 的半径为 40m， 因此 Hack 时必然会受到攻击。

|Portal 等级|攻击伤害|
|:---:|:---:|
|L1|75XM|
|L2|150XM|
|L3|300XM|
|L4|500XM|
|L5|750XM|
|L6|1125XM|
|L7|1625XM|
|L8|2500XM|

> 类似 XMP 对 Resonator 的攻击， Portal 对玩家的攻击也有一定几率发生双倍(Critical Hit)。 

> **被 L8 的 Portal 双倍攻击一次就将损失 5000XM**， 这还是在不计入 Mod 的情况下!
 
> 这也是为什么在高级 Portal 群中使用 XMP 时 XM 损失很快的原因。 

> 使用**Force Amp**可以额外增加伤害， 使用**Turret**可以额外增加双倍攻击概率。 

# Recharge 充能

**Portal 上的 Resonator 每24小时进行一次 Decay。 Resonator 将会损失 XM 上限 15% 的 XM。 **

> 所谓24小时， 是从被占领的一刻算起后24小时: 

> 比如一个 Portal 是当地时间下午三点占领的， 那么当地时间第二天下午三点 Portal 将会 Decay。 

> 事实上， Ingress 中的任何统计均是实时滚动的。 一个满状态的 Portal， 如果不充电不受攻击， 7天会完全 Decay 成中立的状态。 

> 受**游戏剧情影响**这一速度可能会加快。 曾经有出现过每天 Decay 25% 的情况。

**当 Portal 在 Scanner 距离内， 无需 Portal Key 则可直接进行 Recharge。 **

**如在 Scanner 距离外， 则需 Portal Key。 **

> Recharge 效率根据此公式进行计算: 

> **100−distance(km)player.lvl×5 。 **

> 效率在 50% 处截止， 即如果 Portal 远离使得效率\<50%， 则不可 Recharge。 

> 因此每升一级， 最大距离增加 250 km， 距离上限是 4000 km。

Recharge 有两种模式， Recharge All (平均分配 XM 至每个 Resonator) 和 Recharge 单个 Resonator。 

通常 Recharge All， 在对刷等特殊场景时， 有时需要 Recharge 单个 Resonator。

> 每次常规的 Recharge 操作将消耗玩家 1000XM， 实际充入的 XM 将按照效率进行折算。 充电完成后多余的 XM 将会返回给玩家。

> **长按 Recharge All 将可以最多一次性消耗玩家 10000XM 用于 Recharge， 是快速 Recharge 的利器。**

> 每次 Recharge 操作将得到 10AP (无论长按与否)。

# Hack

Hack 操作将会消耗 XM。 数量为 50XM×Portal.lvl 。

如果 Hack 敌方 Portal， 可以得到 100AP， 但还要额外被敌方 Portal 攻击一次。 

> Hack 得到的物品等级取决于玩家等级和 Portal 等级。 

> Portal 的有效等级= min(player.lvl， Portal.lvl)。 

> Hack 可能得到的 XMP 和 Resonator 的等级为 Portal 的有效等级+2-1， 越高等级的概率越低。 

> 可能得到的 Ultra Strike， Power Cube 的等级为 Portal 的有效等级。 比如一个5级玩家 Hack 一个7级 Portal， 他只可能得到: 4-7级的 Resonator 和 XMP， 5级的 Ultra Strike 和 Power Cube。

# Glyph Game

长按**Hack**可以进入**Glyph Game**。 此时需要在规定时间内画出规定数目的Glyph从而获得更多道具。

| Portal有效等级 | 时间上限 | Glyph数目 | Glyph分数 |
|:---:|:---:|:---:|:---:|
|L1|22S|1|1|
|L21|21S|2|2|
|L3|20S|2|2|
|L4|19S|3|4|
|L5|18S|3|4|
|L6|17S|4|8|
|L7|16S|4|8|
|L18|15S|5|15|

> 除了得到更多道具之外， Glyph Game 还可以得到更多 AP (画对一个 Glyph 有 50AP， 全部画对还有速度加成)。 

> 如果所有 Glyph 都没有画错， 可以增加 Glyph 分数以得到 Translator 成就。 得到的 Glyph 分数见上表。

> 进行 Glyph Game 时有一个技巧(仅限于Android): 当Glyph 画错时可以直接点按手机的 Home 键返回桌面。 再次切换进 Ingress 时， 本次 Glyph Game 会中断， 并不计入 Hack。 可以重新再进行一次 Glyph Game。 (当然出现的 Glyph 是不一样的。 )

所有可能出现的 Glyph 图案是有限的， 可以参考 [Glyphtionary][1]。 

实际出现的 Glyph 组合也是有限的， 往往多是一些有意义的词组或短句。 

多加练习， 熟能生巧， 掌握 Glyph Game 并非难事。

# 道具解析

**Resonator**

|等级|能量|部署者XM消耗|每个玩家最多可部署的数量|
|:---:|:---:|:---:|:---:|
|L1|1000XM|50XM|8|
|L2|1500XM|100XM|4|
|L3|2000XM|150XM|4|
|L4|2500XM|200XM|4|
|L5|3000XM|250XM|2|
|L6|4000XM|300XM|2|
|L7|5000XM|350XM|1|
|L8|6000XM|400XM|1|

**注意到部署数量的限制， 一位八级玩家独立部署的 Portal 等级最高为5， 两位玩家为6， 三位八级玩家为 7， 八位玩家为8。**

# 武器

**XMP**

|等级|伤害范围（米）|中心区平均伤害|释放者XM消耗|
|:---:|:---:|:---:|:---:|
|L1|42M|150XM|50XM|
|L2|48M|270XM|100XM|
|L3|58M|470XM|150XM|
|L4|72M|740XM|200XM|
|L5|90M|990XM|250XM|
|L6|112M|1240XM|300XM|
|L7|138M|1580XM|350XM|
|L8|168M|2050XM|400XM|

**此外 XMP 造成伤害时有一定几率造成双倍于上表的伤害(critical hit)。 造成双倍伤害时会数字旁会显示“!”号。**

> 伤害随距离的衰减快于线性， 粗略看与平方衰减更为相似。 

> 不过这一看法并不准确， 因为 XMP 造成的伤害随距离的变化不是连续的， 而是一个分段函数。 (比如对于 L8 的 XMP， 距离每增加约 30m 伤害衰减一次。  ) 

> 关于释放 XMP， 一个重要的技巧是长按 Fire 键可以最多提高20%的伤害， 这粗略相当于提升一个 XMP 伤害等级。 

> **如无特殊情况， 尽量长按 Fire 键释放 XMP**。

> Portal 实际受到的伤害的计算还要考虑 Portal 本身的防御。 

**Ultra Strike**

|等级|伤害范围（米）|最高伤害|释放者XM消耗|
|:---:|:---:|:---:|:---:|
|L1|10M|1300XM|50XM|
|L2|13M|600XM|100XM|
|L3|16M|1000XM|150XM|
|L4|18M|1800XM|200XM|
|L5|21M|2400XM|250XM|
|L6|24M|3000XM|300XM|
|L7|27M|3600XM|350XM|
|L8|30M|5400XM|400XM|

**此外 US 造成伤害时有一定几率造成双倍于上表的伤害(critical hit)。 造成双倍伤害时会数字旁会显示“!”号。**

> 与释放 XMP 类似， 也可以通过**长按 Fire 键提高最多20%的伤害**。

> US 的特点是基本伤害高于同等级 XMP， **双倍伤害的几率很高**。 

> 但其攻击范围小， 随距离衰减极快。 

> **US 最大的用处是在 Portal 中心释放， 可以高效地破除 Portal 上的 Mod。 **

> 当 Res 密集在 Portal 中心时， 也可以考虑使用 US。 (这也反向提示在部署 Res 时尽量分散， 不要集中在 Portal 中心。 )

**病毒**

蓝绿病毒可以强行**改变 Portal 的所有者**。 

> **绿军使用蓝毒， Portal及其上的 Res 和 Mod 的拥有者是 ADA， 蓝军使用绿毒， Portal及其上的 Res 和 Mod 的拥有者是 Javis。 **

> 其他情况下拥有者为病毒使用者本人。

> 病毒本身没有等级， 对使用者也没有直接的等级限制。 

> 但是**在 n 级 Portal 上成功使用病毒， 需要 (1000n+1) 的 XM**。 而 m 级 ( m≤8 ) 的玩家的 XM 上限是 1000(m+2)， 因此 m 级玩家最多可以在 (m+1) 级 Portal 上使用病毒。 比如: 毒掉一个8级 Portal 至少需要一个至少7级的玩家。

> 病毒虽然强力， 但也并非毫无弱点。 病毒的一个重要特性是被病毒改变阵营的 Portal， 一小时内对任何病毒免疫。 **在这一小时的免疫时间内内再次对此 Portal 使用病毒， 无法改变 Portal 阵营且使用的病毒会消失。 **可以利用此特性提前防御性地使用病毒， 防止对方使用病毒。

---- 

[1]:	http://glyphtionary.com

[image-1]:	/img/2017-08-04%2010.25.22.png
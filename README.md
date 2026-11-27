# 官方 3D 卡带外壳模型

为 Continue Arcade 提供 13 款可换色、可贴封面并带背面刻字区的卡带模型。安装后，声明使用这些模型的卡带会在货架和详情页采用对应外观。

此包随应用提供固定版本，也可从 Continue Cart Station 更新。更新后使用新版模型与官方展示配方；撤销更新会恢复应用附带的版本。新版声明需要配套支持资源身份、封面和刻字的客户端。

## 包含模型

| 编号 | 名称 | 编号 | 名称 |
| --- | --- | --- | --- |
| 001 | 地平线 Horizon | 008 | 碧湾 Lagoon |
| 002 | 接力 Relay | 009 | 日芒 Sunburst |
| 003 | 远山 Vista | 010 | 绯弧 Crimson |
| 004 | 城垣 Citadel | 011 | 象牙袖珍 Pocket |
| 005 | 极光 Aurora | 012 | 棱镜 Prism |
| 006 | 星轨 Orbit | 013 | 光谱 Spectrum |
| 007 | 基准灰 Reference | | |

稳定模型编号为 CONTINUE-CART-001 至 CONTINUE-CART-013。012、013 为带电路板细节的透明壳。

## 制作卡带

在自己的 cartfile.toml 中明确声明外观，不依赖按类别猜选：

```toml
[presentation]
cover = "presentation/cover.png"
label = "presentation/label.png"
shell_resource = "org.continue.content.cart-shells"
shell_model = "CONTINUE-CART-006"
shell = "#75658C"
inscription = "love-by-author"
```

cover 是商店用的 2:1 封面；可选 label 是专门贴到卡壳上的图，没有 label 时使用封面。渲染器按模型贴纸区比例居中裁剪，不拉伸图片。图片需位于包的 include 范围内。

刻字模式只有 none、love-by-author、official-keep-playing 和 official-one-more-life。署名模式读取 Cart 的 author，另外两种分别为 KEEP PLAYING. 和 ONE MORE LIFE.。不接受任意刻字字符串。彩蛋文案不构成官方身份或验签证明。

官方逐张外观声明和展示媒体也随本包提供，用于已有内置和官方目录项目的展示，不改写旧业务包的原始字节。已有 Cart 自己声明的外观优先于目录默认配方。

## 社区模型

社区可以发布独立模型资源 Cart。资源使用 type = "content"，以 [cart_shells] manifest = "shells.json" 指向模型清单；安装后客户端从已安装资源目录发现它。模型按「资源 ID / 模型 ID」定位，社区包不占用 org.continue.* 命名空间。

模型清单声明 GLB、前面贴纸材质与画布比例、背面节点与文字安全区、普通与透光调色材质。模型资源是数据，不包含执行脚本。引用社区模型的卡带需要先安装该模型资源包；缺少声明的模型时显示平面封面，不替换成另一款外形。

## 来源与许可

模型及官方贴纸排版由 Continue / karma 制作。业务 Logo 和插画沿用原有素材的署名与许可，未因装入模型包改变归属。详见包内 CREDITS.md 和 LICENSE.txt。

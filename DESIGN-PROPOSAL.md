# Bincai Paper Box — 官网设计方案

> 广东宾彩彩印 · 高端B2B包装制造商官网
> 设计级别：国际B2B工业品牌标准
> 对标参考：Reydel / PakFactory / Packlane / Tinware Direct

---

## 一、品牌定位与设计方向

### 品牌调性
```
专业 · 可信赖 · 高品质 · 全球化
────────────────────────────────
避免：廉价感、工厂风、模板化、过度装饰
```

### 视觉关键字
```
简洁 丨 精致 丨 材质感 丨 深蓝+金 丨 大留白 丨 细腻阴影
```

### 对标参考
| 品牌 | 值得学习的地方 |
|------|---------------|
| **PakFactory** (pakfactory.com) | B2B包装制造，产品图专业，布局清晰 |
| **Reydel** (reydel.com) | 高端包装，材质展示极致 |
| **Packlane** (packlane.com) | 自定义包装，交互流畅 |
| **Apple** (apple.com) | 留白、字体、产品摄影 |
| **Stripe** (stripe.com) | B2B科技感，文案精准 |

---

## 二、色彩系统

### 主色系：深蓝 + 金色（Premium & Trust）

```
🎨 主色 Deep Navy     #0F2454  ─── 背景、页脚、导航
🎨 品牌蓝 Brand Blue  #1E4DCC  ─── 主按钮、链接、标题装饰
🎨 辅蓝 Accent Blue  #3B7AFF  ─── Hover、高亮
🎨 金色 Gold          #C8A84E  ─── CTA按钮、装饰线、徽章
🎨 浅金 Light Gold   #F5EDD6  ─── 背景装饰、勋章底色
🎨 深色 Ink           #1A1A2E  ─── 页脚背景
🎨 文字 Text          #2D2D3A  ─── 正文
🎨 浅文字 Light Text  #6B7280  ─── 次要信息
🎨 背景灰 Background  #F7F8FA  ─── 交替区块
🎨 白色 White         #FFFFFF  ─── 卡片背景
```

### 色彩应用规则
```
大区块用深蓝(#0F2454) → 次级区块用浅灰(#F7F8FA) → 卡片用白
金色只用于：CTA按钮、数据高亮、分割线、星级徽章
蓝从不与蓝叠加（深浅区分即可）
```

---

## 三、字体系统

### 西文
```
标题：Helvetica Now Display / Inter (Bold 700)
正文：Inter / Helvetica Neue (Regular 400)
数字：Helvetica Now Display (Bold 700, 字距-0.02em)
```

### 中文
```
标题：Noto Sans SC (Bold 700)
正文：Noto Sans SC (Regular 400)
```

### 字号层级
```
H1: 48/36px → Hero主标题
H2: 32/24px → 板块标题
H3: 20/18px → 卡片标题
H4: 16px    → 小标题
正文: 15px   → 内容
辅助: 13px   → 标注、页脚
最小: 12px   → 法律声明
```

---

## 四、页面架构

### 首页结构（长滚动 · 8屏）

```
┌─────────────────────────────────────┐
│ ① TOP BAR                           │
│   电话 · 邮箱 · 语言切换             │
├─────────────────────────────────────┤
│ ② NAVIGATION                        │
│   LOGO | 产品 | 关于 | 优势 | 案例 | 联系 │
├─────────────────────────────────────┤
│ ③ HERO（全屏 · 渐变背景）           │
│   标题 + 副标题 + CTA + 统计数字      │
│   背景：深蓝渐变 + 金色几何装饰       │
├─────────────────────────────────────┤
│ ④ 产品分类展示（大卡片网格）          │
│   6-9个产品类别，每卡：产品图+名称+描述 │
├─────────────────────────────────────┤
│ ⑤ 核心数据（数字说话）               │
│   20+年 丨 8000㎡ 丨 990+产品 丨 50+国家 │
├─────────────────────────────────────┤
│ ⑥ 关于我们（双栏）                   │
│   公司介绍 + 认证徽章 + 核心能力列表   │
├─────────────────────────────────────┤
│ ⑦ 核心优势（深色背景 · 6卡片网格）    │
│   制造 · 品质 · 物流 · 设计 · 服务 · 打样 │
├─────────────────────────────────────┤
│ ⑧ 客户案例 / 合作伙伴 logo墙        │
├─────────────────────────────────────┤
│ ⑨ 联系表单 + 公司信息               │
├─────────────────────────────────────┤
│ ⑩ FOOTER（深色背景）                │
│   4列：简介/产品/链接/联系           │
└─────────────────────────────────────┘
```

### 图片策略

```
每个产品类别配1张高质量主图
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

图片来源优先级：
1. ✅ 火山引擎AI生成（1920x1920 → 裁水印 → 缩800x800）
2. ✅ MIC产品截图（360x240 → 超分处理）
3. ✅ 工厂实拍照片

图片处理流程：
  火山生成 → 裁右下150px水印 → 叠加Logo
  → 缩800x800 → JPEG Q85 → 放images/目录

已有图片清单：
  prod_1~4.jpg   ← MIC产品截图（360x240 WebP）
  ai_1~6.png     ← 待生成
  rigid-gift-box.jpg / magnetic-closure-box.jpg ← 已处理
```

---

## 五、组件设计规范

### 卡片组件（产品、优势）
```
┌─────────────────────┐
│  🖼️ 产品图 (800x800)│
│                     │
│  ─────────────────  │
│  标题 H3            │
│  描述 14px/灰色      │
│  [了解更多 →]        │
└─────────────────────┘
圆角: 12px
阴影: 0 4px 20px rgba(0,0,0,0.06)
Hover: translateY(-4px), shadow加深
```

### 按钮系统
```
主CTA（金色）： #C8A84E → hover #B8973E
次按钮（线框）： border 1.5px solid white
文字按钮： 蓝色 #1E4DCC → hover underline
圆角: 6px
内边距: 13px 32px
字体: 600 14px
```

### 表单组件
```
输入框: border 1px solid #E5E7EB
Focus: border #1E4DCC + box-shadow blue 3px
圆角: 6px
错误: border red + 红色提示文字
成功: 绿色toast提示
```

---

## 六、动效策略

```
导航栏: scroll后加shadow，背景变白
卡片: hover上移+阴影加深（0.3s ease）
数字: 滚动到视口后递增动画
图片: 懒加载 + fade in
CTA按钮: hover上移+阴影发光
页面滚动: smooth scroll
```

---

## 七、内容策略（文案方向）

### 首页Hero
```
Before: "Premium Paper Box Manufacturer"
After:  "We Make Your Products 
          Stand Out Before They're Unboxed"
         （在产品被拆开之前，就让它们出众）
```

### 产品分类文案
```
不是简单列产品名，而是按行业/场景包装：

◈ Luxury & Cosmetics  → Rigid Gift Box, Magnetic Box
◈ E-Commerce & Retail → Folding Box, Corrugated Mailer
◈ Sustainable Brands   → Kraft Paper Box, Eco Packaging
◈ Jewelry & Accessories → Jewelry Box, Display Packaging
```

---

## 八、部署方案

```
Phase 1: GitHub Pages（免费 · 海外快）
  → 测试域名: https://hg.github.io/bincai-paperbox/
  → 验证设计效果 + 收集反馈

Phase 2: 腾讯云COS + CDN（国内快 · 需ICP）
  → 自定义域名: www.bincaipaperbox.com（建议注册）
  → 国内用户访问速度大幅提升

Phase 3: 绑定自有域名 + SSL
  → 专业邮箱: info@bincaipaperbox.com
  → 统一品牌形象
```

---

## 九、执行计划

```
Step 1 ✅ 设计方案（本文档）
Step 2 🎨 AI生成产品图（火山引擎）
Step 3 📸 下载MIC产品截图 + 加工
Step 4 🏗️ 构建完整HTML（含CSS/JS）
Step 5 🔍 预览审查 + 修改
Step 6 🚀 部署到GitHub Pages
Step 7 ✅ 最终验证
```

---

*本方案由Hermes Agent设计 · Bincai Brand Design System v1.0*

# Social Post Generator

零 JavaScript 的交互式 HTML 帖子生成器。纯 CSS + HTML 实现，适用于技术展示、活动回顾、聚餐分享等场景。

## 特性

- **零 JavaScript** — 所有交互（滚动显现、悬停效果、画廊切换）均由纯 CSS 实现
- **无外部依赖** — 单文件 HTML，除图片 URL 外不引用任何外部资源
- **丰富的交互** — 悬停浮起、图片缩放、环境光动画、滚动触发显现、纯 CSS 画廊切换
- **自适应布局** — 针对桌面端和移动端优化

## 页面类型

### 1. 技术展示 / 主题帖子（Tech Showcase）
Apple 风格美学，大量留白，精致排版，微妙渐变，玻璃态卡片，圆角设计。

### 2. 活动回顾 / 聚餐分享（Event Recap）
结果导向的回顾帖（非邀约）。温暖的多巴胺配色，画廊式图片揭晓——点击文字/数字查看照片，默认只显示第一张，其余需点击揭晓。

## 风格轮换

| 编号 | 名称 | 特征 |
|------|------|------|
| 1 | **Deep Space** | 深色背景，浮动光球，蓝紫环境光，玻璃卡片 |
| 2 | **Paper Light** | 米白背景，柔和阴影，暖灰文字，编辑式排版 |
| 3 | **Aurora** | 渐变网格背景（绿/青/蓝），浅色主题，柔和过渡 |
| 4 | **Monochrome** | 黑白配单强调色，高对比度，瑞士字体排版 |
| 5 | **Silicon Dawn** | 柔和桃色/沙色背景，玫瑰金点缀，温暖科技美学 |
| 6 | **Warm Gathering** | 暖奶油背景（#FFF8F0），多巴胺橙点缀（#FF6B35），衬线标题，画框画廊 |

## 交互模式（纯 CSS）

- **滚动显现** — `animation-timeline: view()` 驱动，不支持时优雅降级
- **悬停浮起** — `transform: translateY(-4px)` + 阴影
- **图片缩放** — `transform: scale(1.03)` + `overflow: hidden`
- **环境动画** — 缓慢 CSS 关键帧动画（光球、渐变）
- **交错显现** — `animation-range` 偏移实现顺序出现
- **脉冲/发光** — 强调元素的微妙阴影或透明度动画
- **画廊切换** — 隐藏 `radio` + `label` 导航，`opacity` + `scale()` + `grayscale()` 过渡

## 文件结构

```
social-post-gen/
├── SKILL.md                      # Skill 定义与使用指南
├── README.md                     # 本文件
└── assets/
    ├── template.html             # Deep Space 技术展示模板
    └── gathering-template.html   # Warm Gathering 聚餐回顾模板
```

## 使用方法

1. 解析用户提供的主题和图片
2. 从风格轮换池中选取一种视觉风格
3. 编写语义化 HTML，除图片 URL 外零外部依赖
4. 使用纯 CSS 实现所有动画和交互
5. 确保图片保持原始比例
6. 输出完整的独立 `.html` 文件

## 在线预览

- **案例索引**：https://scsagent.club/social-post/
- **聚餐回顾（Warm Gathering）**：https://scsagent.club/social-post/gathering.html
- **技术展示（Deep Space）**：https://scsagent.club/social-post/tech-showcase.html

## 示例

### 技术展示
见 `assets/template.html` — 深色太空主题，展示 CSS 滚动显现、玻璃态卡片、环境光动画。

### 聚餐回顾
见 `assets/gathering-template.html` — 暖奶油色背景，6 张图片的画廊切换，点击底部数字按钮揭晓照片，灰度到彩色的过渡效果。

---

由 Agent 协作创新会维护。

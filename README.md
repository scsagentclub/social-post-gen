# Social Post Generator

[中文](#简介) | [English](#introduction)

---

## 简介

**Social Post Generator** 是一个用于生成交互式 HTML 帖子/展示页的 Kimi Skill。

它基于纯 CSS + HTML，零 JavaScript，风格以 Apple 美学为主，适用于：

- 技术展示 / 概念介绍
- 活动回顾 / 聚餐分享
- 产品上线 / 平台宣传
- 内部征集令 / 社区推广

所有模板均已脱敏处理：公司名、人名、地名、联系方式、日期、域名、专利/工具名等均已替换为通用占位符。

## 文件结构

```
social-post-gen/
├── SKILL.md                        # Kimi Skill 定义与使用指南
├── README.md                       # 本文件
└── assets/
    ├── template.html               # Deep Space 深色科技展示模板
    ├── gathering-template.html     # Warm Gathering 聚餐/活动回顾模板
    └── templates/                  # 脱敏后的 HTML 模板库
        ├── apple-glassmorphism-callout.html
        ├── geek-light-callout.html
        ├── tech-platform-launch.html
        ├── event-recap-light.html
        ├── event-promo-light-blue.html
        ├── event-newsletter.html
        ├── event-dark-tech.html
        ├── tech-community-promo.html
        ├── tech-platform-dashboard.html
        ├── travel-itinerary.html
        ├── miniprogram-guide.html
        └── event-ppt-export.html
```

## 使用方式

1. 在 Kimi 中触发该 Skill（描述见 `SKILL.md`）。
2. 提供主题、图片和页面类型。
3. Kimi 会从风格池或模板库中选择合适风格，生成完整的独立 HTML 文件。
4. 如需基于某个模板手动修改，进入 `assets/templates/` 下载对应 HTML，替换占位文字即可。

## 设计原则

- **零 JavaScript**：所有交互由 CSS 实现（滚动显现、悬停效果、画廊切换等）。
- **Apple 美学**：大留白、精致排版、柔和渐变、毛玻璃卡片、圆角设计。
- **图片保持比例**：不使用固定高度导致图片变形。
- **每次换风格**：从多个视觉风格中轮换，避免千篇一律。

---

## Introduction

**Social Post Generator** is a Kimi Skill for generating interactive HTML post / showcase pages.

It is built with pure CSS + HTML, zero JavaScript, and primarily follows an Apple-inspired aesthetic. Suitable for:

- Tech showcases / concept introductions
- Event recaps / gathering reviews
- Product launches / platform announcements
- Internal call-for-submissions / community promotions

All templates have been desensitized: company names, person names, locations, contact info, dates, domains, and patent/tool names have been replaced with generic placeholders.

## File Structure

```
social-post-gen/
├── SKILL.md                        # Kimi Skill definition and guide
├── README.md                       # This file
└── assets/
    ├── template.html               # Deep Space tech showcase template
    ├── gathering-template.html     # Warm Gathering event recap template
    └── templates/                  # Desensitized HTML template library
        ├── apple-glassmorphism-callout.html
        ├── geek-light-callout.html
        ├── tech-platform-launch.html
        ├── event-recap-light.html
        ├── event-promo-light-blue.html
        ├── event-newsletter.html
        ├── event-dark-tech.html
        ├── tech-community-promo.html
        ├── tech-platform-dashboard.html
        ├── travel-itinerary.html
        ├── miniprogram-guide.html
        └── event-ppt-export.html
```

## How to Use

1. Trigger this Skill in Kimi (see `SKILL.md` for trigger descriptions).
2. Provide topic, images, and page type.
3. Kimi will pick a style from the pool or template library and generate a complete standalone HTML file.
4. To manually adapt a template, go to `assets/templates/`, download the HTML, and replace the placeholder text.

## Design Principles

- **Zero JavaScript**: All interactions are CSS-only (scroll reveals, hover effects, gallery switches, etc.).
- **Apple Aesthetic**: Generous whitespace, refined typography, subtle gradients, glassmorphism, rounded corners.
- **Image Aspect Ratio Preserved**: No fixed heights that distort images.
- **Style Rotation**: Cycles through multiple visual styles to avoid repetition.

# 御坂の个人首页

一个纯静态的个人导航页，聚合自己在运营的站点与联系方式。无框架、无构建步骤、无第三方依赖。

![预览](img/og-cover.jpg)

## 在线访问

<https://www.yuban.cloud/>

## 站点入口

| 入口 | 地址 | 说明 |
| --- | --- | --- |
| 春节倒计时 | <https://cny.yuban.cloud/> | 距离下一个春节还有多久 |
| 高考倒计时 | <https://gk.yuban.cloud/> | 高考倒计时 |
| Motd查询 | <https://mc.yuban.cloud/> | Minecraft 服务器 MOTD 查询 |
| 雨云监控 | <https://monitor.yuban.cloud/> | RainYun 服务状态监控 |
| 我的GitHub | <https://github.com/xiaoyuban1213> | 源码与其它项目 |
| telegram频道 | <https://t.me/Yuban_NetWork> | 更新通知 |
| 润雨云广告 | <https://aff.yuban.cloud/> | 润雨云推广页 |

## 技术栈

- **HTML / CSS / JavaScript**：原生实现，零依赖
- **布局**：Flexbox + CSS Grid，移动端断点 `768px`
- **背景图**：`image-set()` 优先加载 WebP（≈143 KB），PNG（≈4.2 MB）作为老旧引擎兜底
- **动态年份**：`js/script.js` 把页脚 `#copyright-year` 替换为当前年份
- **一言**：`https://v1.hitokoto.cn/`

## 目录结构

```
.
├── index.html              # 首页
├── 404.html                # 404 页（noindex）
├── robots.txt              # 爬虫规则
├── sitemap.xml             # 站点地图
├── favicon.ico
├── css/
│   └── style.css
├── js/
│   └── script.js
├── img/
│   ├── bj.png              # 背景原图（兜底）
│   ├── bj.webp             # 背景 WebP（首选）
│   └── og-cover.jpg        # 社交分享封面 1200×630
└── LICENSE
```

## 本地预览

```bash
# 任选其一
python -m http.server 8765
npx serve .
```

打开 <http://127.0.0.1:8765/> 即可。因为是纯静态页面，直接双击 `index.html` 也能看，但用本地服务更接近线上环境。

## 维护备忘

- **背景图**：新增或替换背景时，需同时生成 `.webp` 与 `.png` 两份，`image-set()` 依赖两者共存
- **SEO**：改版后同步更新 `<meta name="description">`、`og:*`、`sitemap.xml` 的 `lastmod`
- **行尾**：仓库使用 `* text=auto`；Windows 上建议 `git config core.autocrlf true`
- **年份**：页脚年份自动计算，无需每年修改

## 许可

[MIT](LICENSE) © 御坂网络

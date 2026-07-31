# 个人作品集 · 交接文档

> 项目路径：`秋招简历/portfolio/`
> 主文件：`index.html`
> 交接时间：2026-07-31

---

## 文件结构

```
portfolio/
├── index.html                # 主页面（所有内容在此，单文件应用）
├── HANDOFF.md                # 本文件
├── CHANGELOG.md              # 历史修改记录
└── assets/
    ├── photos/
    │   └── hero.jpg           # 首屏/教育页/关于我共用照片
    └── certs/
        ├── model_apec_1.png   # MODEL APEC 地区赛一等奖
        ├── model_apec_2.png   # MODEL APEC 国赛杰出代表
        ├── jingshibei.png     # 京师杯论文二等奖
        ├── first_scholarship.png
        ├── three_good.png     # 三好学生
        ├── excellent_member.png
        ├── best_student.png   # 优秀学生干部
        ├── qinhuai_letter.png # 秦淮灯会政府感谢信
        ├── qinhuai_service.png
        ├── volunteer_award.png
        ├── volunteer_hours_2025.png
        └── nju_volunteer_hours.png  # 第二课堂 75.5h
```

---

## 页面模块一览

| 模块 | 说明 |
|---|---|
| **Welcome（首屏）** | 全屏瀑布流第一页，左侧双语欢迎语「Hi, welcome to. / 你好，欢迎来到黄钰茜的世界」，右侧沿用现有头图 |
| **Education（教育页）** | 全屏瀑布流第二页，左侧照片 + 北京→南京路径卡片，右侧南京大学–JHU SAIS 与北京师范大学学历卡片 |
| **Navigation（导航）** | 顶部固定导航 + 全屏覆盖式菜单，按钮顺序：Internship / Portfolio / Honors / About me / Contact me |
| **Internship（实习经历）** | 垂直时间线，自下而上为「由远到近」时间顺序；点击节点从右侧滑出详情面板 |
| **Portfolio（作品集）** | 上方两个「工具箱」按钮：内容创作类 / AI 能力类；下方切换展示对应作品 |
| **Honors（荣誉证书）** | 书架设计，3 本书（竞赛与表达 / 学业表现 / 志愿与社会服务），点击书脊展开证书列表，点击证书打开 PDF |
| **About me（关于我）** | ESFJ 人格徽章 + 兴趣爱好照片墙（旅行 / 乒乓球 / 摄影 / 阅读 / 美食 / 音乐）|
| **Contact me（联系我）** | 邮箱、简历下载、回到顶部 |

---

## 交互 & JS 数据说明

- 首屏滚动吸附：`html` 设置 `scroll-snap-type: y proximity`，`#welcome`、`#education` 设置 `scroll-snap-align: start`
- 导航菜单：点击右上角汉堡按钮展开/收起全屏菜单，菜单链接带平滑滚动
- 实习经历数据 → `INTERNSHIPS`（8 段经历，自下而上按时间由远到近排列）
- 作品集数据 → `CONTENT_WORKS`（内容创作类）、`AI_WORKS`（AI 能力类，含 dims 与 cases）
- 证书数据 → `CERT_BOOKS`（3 组共 12 项，`pdf` 指向 `assets/certs/` 本地图片）
- 兴趣爱好数据 → `HOBBIES`（6 项，照片墙占位）
- 详情面板：`detail-panel` 固定右侧滑出，点击遮罩或 × 关闭
- 证书灯箱：点击证书同时在新标签页打开 PDF 并在灯箱中预览图片

---

## 给下一个 agent 的注意事项

1. **头图**：首屏、教育页、关于我共用 `assets/photos/hero.jpg`。如需替换，直接替换该文件或在对应 `<img>` 中修改 `src`。
2. **教育页照片**：当前复用 `hero.jpg`。如提供毕业照或校园照，可替换 `.edu-photo img` 的 `src`。
3. **兴趣爱好照片墙**：6 个位置目前是占位符。插入真实照片时，把对应 `.about-img` 内部替换为 `<img src="你的图片路径">` 并给 `.about-img` 加上 `class="has-img"`。
4. **作品链接**：内容创作类中的公众号/文章链接当前为 `#` 占位，补充真实 URL 即可。
5. **实习经历**：数据来自 `/Users/amy/Desktop/小满/秋招简历/小满星简历（全）.docx`，如需增删经历，直接修改 `INTERNSHIPS` 数组。
6. **配色**：CSS 变量在 `:root` 中定义（`--bg` 浅蓝 / `--neon` 品牌蓝 / `--teal` 青色等），直接修改变量即可全局换色。
7. **本地打开**：`index.html` 直接双击在浏览器中打开即可预览（所有路径为相对路径），无需服务器。

# 厢间人 — The Man in Between

> 仿《极乐迪斯科》(Disco Elysium) 的后末日火车文字冒险 Web 游戏 · 本地化课程Vibe Coding项目，仅包含游戏背景世界观设计，大纲设计与游戏框架搭建

[English](#english)

---

## 简介

**厢间人** 是一款受《极乐迪斯科》启发的文字冒险 Web 游戏。故事发生在后末日世界——一种名为"空海"的雾状物质吞噬了大部分陆地，文明被分隔成孤岛。主角在诺斯塔吉亚号列车（K城 → A城）的车厢中醒来，失去了所有记忆。

你是谁？老妇人失散多年的儿子？双手沾血的杀人犯？还是空海本身凝聚的某种意识体？——

纯 HTML/CSS/JS 单文件引擎，零框架依赖。支持**中英双语热切换**，开箱即用。

---

## 特色

- **2d6 骰子检定系统**：六项技能 × 三级属性（智识/灵性/肉体），检定 DC 由难度直接决定
- **中英双语热切换**：游戏内按键（Q）秒切语言，对话日志完整重放，UI 文案数据库化
- **问卷系统**：8 题初始化问卷，分配初始属性点
- **物品与双血条**：HP + 理智值，任一归零游戏结束
- **循环对话**：已选选项视觉褪色，不可重复选择
- **存档系统**：localStorage 自动/手动存档
- **自研剧本编译器**：Markdown → JavaScript，支持场景、物品、技能检定、循环对话等语法
- **Excel 协作工作流**：UI 文案和问卷可通过 Excel 编辑后一键导入

---

## 快速开始

```bash
# 1. 克隆仓库
git clone <repo-url>
cd gameproject

# 2. 编译剧本（如果修改过剧本源文件）
node 剧本/build.js

# 3. 直接用浏览器打开 index.html
```

> 无需 `npm install`、无需本地服务器——打开 `index.html` 即可游玩。

---

## 文件结构

```
gameproject/
├── index.html              ← 游戏主引擎 (2281行)，三栏布局 + 骰子系统 + 存档
├── js/
│   ├── i18n.js             ← UI 文案数据库（中英双语，T() 取值）
│   ├── i18n_export.py      ← i18n.js ↔ i18n.xlsx 互转脚本
│   ├── quiz.js             ← 问卷数据库（中英双语，索引化权重）
│   ├── quiz_export.py      ← quiz.js ↔ quiz.xlsx 互转脚本
│   ├── script_zh.js        ← 中文剧本（编译产物，禁止手动编辑）
│   └── script_en.js        ← 英文剧本（编译产物，禁止手动编辑）
├── assets/                 ← 静态资源（场景图、物品图、UI图、视频、音频）
├── 剧本/
│   ├── script_zh.md        ← ★ 中文剧本源文件（主编辑目标）
│   ├── script_en.md        ← ★ 英文剧本源文件
│   ├── build.js            ← 剧本编译器 Markdown → JS
│   ├── syntax_reference.md ← Markdown 剧本语法完整参考
│   └── 完整版备份/          ← 四章完整版备份（参考用）
├── 设计文档/
│   ├── 剧情大纲与结局分支.txt
│   ├── 色卡.txt
│   └── 游戏Demo设计文档.docx
├── i18n.xlsx               ← UI 文案 Excel（导出/导入编辑）
├── quiz.xlsx               ← 问卷 Excel
└── README.md
```

---

## 开发工作流

| 改什么 | 改哪里 | 需要编译 |
|--------|--------|----------|
| 剧本对话 | `剧本/script_zh.md` / `script_en.md` | `node 剧本/build.js` |
| UI 文案 | `i18n.xlsx` → `python js/i18n_export.py --import` | 否 |
| 问卷 | `quiz.xlsx` → `python js/quiz_export.py --import` | 否 |
| 引擎/UI/CSS | `index.html` | 否 |

```bash
# 编译剧本
node 剧本/build.js

# 导出 i18n 到 Excel
python js/i18n_export.py

# 从 Excel 导入 i18n
python js/i18n_export.py --import

# 同上，quiz
python js/quiz_export.py
python js/quiz_export.py --import
```

---

## 游戏系统

### 六项技能（2d6 + 属性 ≥ DC）

| 属性 | 技能（中文） | 技能（英文） | 索引 |
|------|-------------|-------------|------|
| 智识 | 哲学思辨 | Philosophical Thought | 0 |
| 智识 | 逻辑推导 | Logical Deduction | 1 |
| 灵性 | 缪斯女神 | The Muse | 2 |
| 灵性 | 灵魂叙事 | Soul Narrative | 3 |
| 肉体 | 技术专家 | Technical Expert | 4 |
| 肉体 | 身强体壮 | Physical Might | 5 |

### 双血条

- **HP**：3/3 → 0 则身体崩溃
- **Sanity（理智）**：2/3 → 0 则精神崩溃
- 物品可恢复：`white_pill`（理智 +1）、`faded_thread`（HP +1）

### 剧本语法示例

完整语法参考 `剧本/syntax_reference.md`。

```markdown
# 第一章：醒来                    ← 场景
@bg: assets/bg_车厢.png          ← 背景图声明
@music: assets/轨道_no-watermark.mp3  ← 音乐声明

## wake_up                        ← 节点 ID
### 旁白                          ← 旁白叙述
你睁开眼睛，头顶是陌生的天花板。

### 你                            ← 玩家内心
「我……是谁？」

### 哲学思辨                      ← 技能发声（仅 UI 展示，不检定）
这些问题没有答案，但提问本身就是一种姿态。

? 环顾四周 → look_around          ← 选项跳转
? 继续躺着 → stay_in_bed

? [逻辑推导 难度:11] 试图拼凑记忆碎片 → 成功:memory_ok | 失败:memory_fail
                                  ← 技能检定（2d6 + 逻辑推导 ≥ 11）
```

---

## 技术架构

```
script_*.md  ──build.js──▶  js/script_*.js  ──<script>──▶  window.SCRIPT_ZH/EN
i18n.js ──<script>──▶  window.I18N  ──T()──▶  所有 UI 文本
quiz.js ──<script>──▶  window.QUIZ_ZH/EN  ──QUIZ()──▶  问卷
```

- **CSS 变量系统**：极乐迪斯科风格暗色调色板
- **属性索引化**：`STATE.stats = [3,4,2,5,1,2]`，语言无关的数字索引
- **对话日志重放**：切换语言时遍历日志 → 从新脚本重读节点 → 无闪烁切换
- **存档键**：`xiangjianren_save`（localStorage）

---

## 快捷键

| 按键 | 功能 |
|------|------|
| `Q` | 切换中/英文 |
| `Esc` | 打开/关闭设置面板 |
| `Space` | 推进对话 |

---

## 配色

| 色名 | 色值 | 用途 |
|------|------|------|
| 苔绿 | `#2B3834` | 背景底色 |
| 靛青 | `#3D577C` | UI 强调色 |
| 湖蓝 | `#4B6493` | 智识属性 |
| 烟蓝 | `#748195` | 次级文字 |
| 艾绿 | `#5A6355` | 成功绿 |

---

## 致谢

- 游戏设计灵感来自 ZA/UM 的《极乐迪斯科》(Disco Elysium)
- 本项目为本地化课程的实践作业，感谢曹婷的美术辅助

---

## English

**The Man in Between** (*Xiāng Jiān Rén*) is a post-apocalyptic train text adventure web game inspired by *Disco Elysium*. Built as a localization course project.

- **Zero dependencies**: pure HTML/CSS/JS single-file engine
- **Bilingual**: Chinese/English hot-swap at runtime (press `Q`)
- **2d6 skill check system**: 6 skills across 3 attributes (Intellect/Spirit/Body)
- **Custom Markdown → JS compiler**: write dialogue in Markdown, compile to playable script
- **Play instantly**: open `index.html` in any browser — no build step required

### Story

The *Nostalgia* — the first train to attempt a crossing of the Sea of Void — is on its maiden voyage from K-City to A-City. You wake in a compartment with no memories. The passengers seem to know things about you that you don't. A mother believes you're her lost son. A detective's memories bleed into yours. And the Sea of Void is rising.

### Quick Start

```bash
git clone <repo-url>
cd gameproject
node 剧本/build.js    # compile scripts (optional, pre-built files included)
open index.html       # play directly in browser
```

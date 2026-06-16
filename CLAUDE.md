# 厢间人 (The Man in Between)

仿《极乐迪斯科》的后末日火车文字冒险 Web 游戏 demo，本地化课程项目。纯 HTML/CSS/JS 单文件架构，无框架依赖。

## 文件结构

```
gameproject/
├── index.html              ← 游戏主引擎，三栏布局 + 骰子系统 + 存档
├── js/                     ← ★ 所有 JS 和转换脚本
│   ├── i18n.js             ← UI 文案数据库（中英双语，T() 取值）
│   ├── i18n_export.py      ← i18n.js ↔ i18n.xlsx 互转
│   ├── quiz.js             ← 问卷数据库（中英双语，索引化权重）
│   ├── quiz_export.py      ← quiz.js ↔ quiz.xlsx 互转
│   ├── script_zh.js        ← 中文剧本（由 build.js 自动生成，禁止手动编辑）
│   └── script_en.js        ← 英文剧本（由 build.js 自动生成，禁止手动编辑）
├── assets/                 ← 静态资源（场景图、物品图、UI图、视频、音频）
├── 剧本/
│   ├── script_zh.md        ← ★ 中文剧本源文件（主编辑目标）
│   ├── script_en.md        ← ★ 英文剧本源文件
│   ├── build.js            ← 剧本编译器 Markdown → JS（输出到 ../js/）
│   ├── syntax_reference.md ← Markdown 剧本语法完整参考
│   └── 完整版备份/          ← 四章完整版备份
├── 设计文档/
│   ├── 剧情大纲与结局分支.txt
│   ├── 色卡.txt
│   └── 游戏Demo设计文档.docx
├── i18n.xlsx               ← UI文案 Excel（导出/导入编辑）
├── quiz.xlsx               ← 问卷 Excel
├── 叙述文案.xlsx            ← 叙述文案（旧版，已迁移到 i18n）
└── CLAUDE.md
```

## 开发工作流

```
编辑剧本    →  node 剧本/build.js  →  生成 js/script_*.js  →  浏览器打开 index.html
编辑UI文案  →  修改 i18n.xlsx     →  python js/i18n_export.py --import
编辑问卷    →  修改 quiz.xlsx     →  python js/quiz_export.py --import
```

- **必须先 `cd` 到项目根目录再运行**：`cd "F:/德语学习/本地化/gameproject" && node 剧本/build.js`
- i18n/quiz Excel 互转：`python js/i18n_export.py`（导出）/ `--import`（导入）

## 引擎架构

`index.html` 是自包含的单文件引擎：

- **CSS (~400行)**：极乐迪斯科风格变量系统、覆盖层、三栏布局、骰子动画
- **JS (~1300行)**：游戏循环 + 双语热切换 + 问卷 + 存档

### 中英双语热切换系统

**属性索引化**：`STATE.stats = [3,4,2,5,1,2]`（0-5 数字索引，语言无关）。`STAT_IDX` 映射表将脚本技能名（中/英）统一转为索引。

**UI 文案**：`js/i18n.js`（`window.I18N`），`T(key)` 取值。覆盖菜单、面板、弹窗、骰子、叙述文案。

**对话日志重放**：`dialogueLog` 记录 `{type:"node"/"choice"/"check", ...}`。切换语言时清屏 → 遍历日志 → 节点从新脚本重读 → 秒切。

**Q 键/设置面板/语言按钮** → `settingsToggleLang()` 统一入口，刷新全部界面。

### 数据流

```
script_*.md  ──build.js──▶  js/script_*.js  ──<script>──▶  window.SCRIPT_ZH/EN
i18n.js ──<script>──▶  window.I18N  ──T()──▶  所有 UI 文本
quiz.js ──<script>──▶  window.QUIZ_ZH/EN  ──QUIZ()──▶  问卷
```

## 剧本语法速查

完整语法见 `剧本/syntax_reference.md`。

**物品定义**：`@item id ... @enditem`，属性 `name/desc/usable/effect/consume`

**场景**：`# 场景名称`，可选 `@bg:` `@music:` `@volume:`
- 场景头部声明 → 整场有效
- 节点前声明 → 仅该节点起生效，后续节点粘住不自动回退

**节点**：`## node_id`，说话人 `### 旁白` / `### 你` / `### 角色名` / `### 技能名`
- 角色节点只放 `「」`对话，描述性文字分离到 `### 旁白`
- 多人对话拆分到各自节点

**选项**：`? 选项文字 → next_id [&loop] [@effects]`

**技能检定**：`? [技能名 难度:N] 描述 → 成功:ok | 失败:fail [&loop]`
- N 直接决定 DC，无硬编码映射（英文标签 `Simple/Easy/Medium/Hard` 同样支持）

**循环对话**：选项加 `&loop`，响应节点结尾 `→ &return`。已选选项半透明不可再点。

**特殊标记**：`@end` `@inputName` `---`

## 游戏系统

### 六项技能（2d6 + 属性 ≥ DC）

| 属性 | 技能 | 索引 |
|------|------|------|
| 智识 | 哲学思辨 / Philosophical Thought | 0 |
| 智识 | 逻辑推导 / Logical Deduction | 1 |
| 灵性 | 缪斯女神 / The Muse | 2 |
| 灵性 | 灵魂叙事 / Soul Narrative | 3 |
| 肉体 | 技术专家 / Technical Expert | 4 |
| 肉体 | 身强体壮 / Physical Might | 5 |

- 双血条：HP 3/3，Sanity 2/3
- 物品：`white_pill`（理智+1）、`faded_thread`（HP+1）
- 存档：localStorage，键 `xiangjianren_save`

### 问卷

8 题 × 3 选项，每题 2 点，总分 16。权重在 `js/quiz.js`，索引用 `{1:1, 4:1}` 格式。Excel 可编辑。

## 设计约束

1. 文本风格模仿极乐迪斯科，有文学性
2. 西方命名，东西方文化混合
3. 车厢是意识隐喻空间，不出现照片类实物
4. **诺斯塔吉亚号是第一次跨空海试运行**（非运营多年的老线路）
5. 角色对话分离：`### 角色名` 仅含 `「」`对话，描述归 `### 旁白` 或技能发声

## 编辑指南

| 改什么 | 改哪里 | 需要编译 |
|--------|--------|----------|
| 剧本对话 | `剧本/script_zh.md` / `script_en.md` | `node 剧本/build.js` |
| UI 文案 | `i18n.xlsx` → `python js/i18n_export.py --import` | 否 |
| 问卷 | `quiz.xlsx` → `python js/quiz_export.py --import` | 否 |
| 引擎/UI/CSS | `index.html` | 否 |

- `js/script_zh.js` / `js/script_en.js` 是编译产物，禁止手动编辑
- `剧本/完整版备份/` 是四章完整版，仅作参考

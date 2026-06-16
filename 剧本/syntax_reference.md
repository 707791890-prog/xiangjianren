# 厢间人 剧本语法参考

> 编辑 `script_zh.md` 或 `script_en.md` 后，运行 `node 剧本/build.js` 重新生成 JS。

---

## 物品模板

在剧本最顶部定义所有物品，每个物品用 `@item` / `@enditem` 包裹。

```
@item 物品ID
name: 物品名称
desc: 物品描述文本
usable: true或false（是否可使用）
effect: sanity_restore 数值  或  hp_restore 数值（可选）
consume: true或false（使用后是否消耗）
bullets: 数字（可选，弹夹容量等额外信息）
@enditem
```

**示例**:
```
@item white_pill
name: 白色药片
desc: 散发着青草气息的白色药片。标签已经模糊了。
usable: true
effect: sanity_restore 1
consume: true
@enditem
```

**物品图片**: 将图片命名为 `assets/item_{物品ID}.png`（如 `assets/item_white_pill.png`），物品详情弹窗会自动加载。没有图片时无痕降级。

---

## 场景

### 场景标题
```
# 场景名称
```

### 场景属性
```
@bg: assets/bg_场景名.png     ← 背景图（可选）
@music: assets/bgm_场景名.mp3  ← 背景音乐（可选）
```

**注意**: 背景和音乐文件命名约定：`bg_{场景名}.png`、`bgm_{场景名}.mp3`，放在 `assets/` 目录下即可被自动检测。

---

## 对话节点

### 基本结构
```
## 节点ID
### 说话人
对话文本内容。

可以有多段。

→ 下一个节点ID
```

### 说话人标签
- `### 旁白` — 叙述者，琥珀色
- `### 你` — 玩家，暖白色
- `### 人物名` — NPC（如 `### 安沙`），紫色
- `### 技能名` — 技能检定（如 `### 逻辑推导`），蓝色

### 文本中的变量
- `{playerName}` — 会被替换为玩家输入的名字

---

## 分支与推进

### 自动推进（无选项）
```
→ next_node_id
```
文本显示完毕后出现"点击继续"提示，点击后进入下一节点。

### 自动推进 + 效果
```
→ next_node_id @addItem:pistol @sanity:1 @hp:-1 @removeItem:key
```
支持的标签：`@addItem:ID` `@removeItem:ID` `@sanity:N` `@hp:N` `@inputName`

### 玩家选项
```
? 选项文字 → 下一节点ID
? 把药片收起来。 → save_pill @addItem:white_pill
```

---

## 循环对话（Hub）

玩家可以反复回到同一个节点，每次已选过的选项会变暗。适用于"向NPC提问"等场景。

### Hub 节点

选项末尾加 `&loop` 标记，留一个不带标记的选项作为"离开"。

```
## hub_talk
### Ansel
"你想聊什么？"

? "关于这列火车" → hub_train &loop
? "关于你自己" → hub_ansel &loop
? "关于空海" → hub_void &loop
? "没什么了。" → next_scene
```

### 响应节点

结尾用 `→ &return` 自动返回 Hub。

```
## hub_train
### Ansel
"诺斯塔吉亚号，K城到A城，第一条跨空海铁轨。"

→ &return
```

### 行为说明

- 选 `&loop` 选项 → 播放响应节点 → **自动回到 Hub**
- 回到 Hub 时已选过的选项以半透明显示（35% 透明度），不可再次点击
- 不带 `&loop` 的选项正常推进剧情
- `&return` 节点也可以附加效果标签：`→ &return @sanity:+1`

### 循环 + 技能检定

检定选项同样支持 `&loop`，成功和失败路径都需要以 `&return` 结尾：

```
? [逻辑推导 中等:9] 分析引擎的异常噪音 → 成功:hub_engine_ok | 失败:hub_engine_fail &loop
```

```
## hub_engine_ok
### 逻辑推导
你听出来了——是冷却系统的问题，不严重。

→ &return

## hub_engine_fail
### 逻辑推导
声音在你脑子里搅成一团。你什么都分辨不出来。

→ &return
```

### 命名约定

- `hub_` 前缀和 `&return` 都不是强制的——引擎只认 `&loop` 和 `&return` 这两个标记
- 任何节点都可以作为 Hub（只要它的选项带 `&loop`），任何节点都可以用 `→ &return` 回到上一个 Hub
- 建议 Hub 节点用 `hub_` 前缀、响应节点用对应名称，便于阅读和维护

---

## 技能检定

### 单结果检定（仅判成败）
```
? [技能名 难度:N] 描述文字 → 下一节点
```
难度标签映射：`简单`=7, `中等`=9, `困难`=11

### 双分支检定（成功/失败不同走向）
```
? [技能名 难度:N] 描述文字 → 成功:成功节点ID | 失败:失败节点ID
```

### 示例
```
? [逻辑推导 简单:7] 冷静地分析这个空间的结构。 → 成功:analyze_room_success | 失败:analyze_room_fail
? [灵魂叙事 中等:9] 这把枪在跟你说话。 → 成功:pistol_speaks | 失败:pistol_silent
```

---

## 特殊标记

| 标记 | 用途 | 位置 |
|------|------|------|
| `@end` | 终止节点（无后续） | 独立一行 |
| `@inputName` | 触发姓名输入弹窗 | 跟在 `→` 或选项后 |
| `---` | 节点分隔符（可选） | 独立一行 |

---

## 效果标签汇总

| 标签 | 示例 | 效果 |
|------|------|------|
| `@addItem:ID` | `@addItem:pistol` | 添加物品到背包 |
| `@removeItem:ID` | `@removeItem:key` | 从背包移除物品 |
| `@sanity:N` | `@sanity:1` 或 `@sanity:-2` | 增加/减少精神值 |
| `@hp:N` | `@hp:-1` 或 `@hp:2` | 增加/减少生命值 |
| `@inputName` | `@inputName` | 弹出姓名输入框 |

效果标签可叠加使用，用空格分隔：`→ next_id @addItem:sword @hp:-1 @sanity:1`

---

## 完整示例

```
@item white_pill
name: 白色药片
desc: 散发着青草气息的白色药片。
usable: true
effect: sanity_restore 1
consume: true
@enditem

# 开场
@bg: assets/bg_开场.png

## wake_up
你醒了。

你的后脑勺贴着一块冰凉的金属。

→ first_look

---

## first_look
### 旁白
你睁开眼。

天花板很低。铆钉。

? 环顾四周。 → look_around
? 「有人吗？」 → call_out
```

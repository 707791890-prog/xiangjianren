@item white_pill
name: 白色药片
desc: 散发着青草气息的白色药片，闻起来让人感到心神安定。你不知道这是什么药，但你隐约明白了它的作用。
usable: true
effect: sanity_restore 1
consume: true
@enditem

@item faded_thread
name: 褪色的线头
desc: 一根褪了色的红线头，大概是从某件旧西装上脱落的。你攥在手里的时候，会觉得安心——像是攥着某个人的袖口。
usable: true
effect: hp_restore 1
consume: true
@enditem

# 开场
@bg: assets/bg_意识的诞生.png
@music: assets/灰雾_no-watermark.mp3

## wake_up
### 旁白
你醒了。

不，准确地说——你正在醒来。你察觉到自己漂浮在某个边界上，左边是深海般的幽黑，如同黑洞，它正在旋转，吞噬着一切目光，连观测也不被允许。回过头，右边是某种灰白色牛乳般的空间。灰色的游鱼倏忽而来，又倏忽而逝。

→ feeling_something_in_the_dark

---

## feeling_something_in_the_dark
### 旁白
它们的触碰让你隐隐发痒。仿佛有什么东西在注视你，刺骨的寒冷开始在你的大脑皮层上爬动，发出哇哇孩童般的哭声，潮湿、黏稠的液体在空荡荡的头颅尖端凝聚，滴落，一丝臭氧和鱼腥味弥漫开来。还有一种电的味道。

笑声在遥远的地方拉起了宇宙的辰星，一道名为人生的幕布即将就此被拼接而成。

? 等等，电是什么味道？ → electric_feel
? 有点恐怖，我不想醒来。 → do_not_wake_up1

---
## electric_feel
### 旁白
这个世界的医院每天会迎来5、6万的新生儿，大多数新生都伴随着手术室闪烁的灯光。门外，红灯变成绿灯；门内，电流之间的人露出欣慰的神情，有的护士会轻轻拍打婴儿的背，让哭不出的孩子发出声音。

从人工电到生物电，于是有人说电流是蛋白质的味道。但那可能只是触电造成的。

? [灵魂叙事 简单:5] 我怎么听到了骰子的声音？ → 成功:first_try_success | 失败:first_try_fail
? 够了，别乱想了，我要醒来。 → first_look

---

## do_not_wake_up1
### 旁白
黑暗的水散发出淡淡的铁锈味，这是因为有一把枪在你面前融化了。

融化：并不是由于温度的增高，而是因为温度这一概念的消失。你预感到那尚未成形的听觉和视觉也在离你远去，你将再也看不见那数道身影，骰子还在滚动，但你已经听不见了。

? [灵魂叙事 简单:5] 这不是还有骰子吗？试一试 → 成功:first_try_success | 失败:first_try_fail
? 算了，就这样吧。 → do_not_wake_up2

---

## first_try_success
### 旁白
对的！没错！骰子的声音！那令人着魔的声音！

来吧，把生命再度交给骰子，从那湿润的黑暗中离开！

? 我要醒来。 → first_look
? 到此为止，晚安。 → do_not_wake_up2

---

## first_try_fail
### 旁白
没有什么骰子，错觉，光怪陆离的错觉。

古旧的楼房墙面上攀满了爬山虎，在傍晚时分，城市的砖墙是最红的。在那叶片下的阴影里，有什么东西总是在凝望着你。然而你连这些也看不见了。

→ do_not_wake_up2

---

## do_not_wake_up2
### 旁白
你蜷缩起来，如果你能控制你的四肢的话；
你保持沉默，如果你还能控制气流的话；
你睡着了，如果你还真的能有意识的话。

那些灰色鱼儿又来了，柔软的灰，每一条鱼都是一个更庞大存在的手指，这千指之手攀附上了你不存在的身体，包裹着你，爱抚着你。

然后从那人类漫长的历史中，你听见一声可怕的枪响。

@end

---
@bg: assets/bg_车厢.png
@music: assets/轨道_no-watermark.mp3
@volume: 0.2

## first_look
### 旁白
你睁开眼。

天花板很低。铆钉。金属板拼接的痕迹。一盏昏黄的灯在有节奏地微微晃动，光也跟着晃动——像是在水里。

你听到一种低沉的、持续的嗡鸣声。不是耳鸣。是从墙壁里传来的。

→ stand_up

---

## stand_up
### 旁白
你试图站起来。腿是软的——不是因为虚弱，而是一种更根本的陌生感，好像这些肌肉不是你的，好像你还不确定自己和这具身体是什么关系。

你扶着墙站住了。墙壁在震动。

? 环顾四周。 → look_around
? 「有人吗？」 → call_out

---

## look_around
### 旁白
这是一节火车车厢。

但不太对劲。车厢的一侧有一扇窗户——长方形的，玻璃上蒙着一层灰，外面的东西看不清楚。你靠近窗户，用手擦了擦玻璃。

灰在外面。

玻璃内侧是干净的。那种灰——或者不是灰——均匀地贴在玻璃的另一面，像某种雾，但又比雾更……实在。它既流动又凝固，既像气体又像织物。你盯着它看了几秒，感到一种说不清的不安——不是因为它可怕，而是因为它让你想起了什么东西。你只是不记得是什么了。

→ try_window

---

## try_window
### 旁白
你试着推了推窗户。锁死的。或者根本就没有锁——它看起来更像是被焊接封住的。你用手指敲了敲玻璃，声音闷闷的，像是敲在浸了水的木板上。

窗户外面那个灰蒙蒙的东西没有反应。当然不会有反应。那又不是活的。

……对吧？

→ notice_no_door

---

## call_out
### 你
「有人吗——有没有人——」

→ voice_responds

---

## voice_responds
### 旁白
你的声音在车厢里弹了两下就死了。这节车厢太小了——一个隔间大小——容不下回声。

但然后你听到了什么。

从墙壁的另一侧。不是回声。是一个人的声音。

→ ansel_appears

---

## notice_no_door
### 旁白
你转身，目光扫过车厢的四壁。

有窗的那面墙。

对面是沙发——一张旧的、皮质开裂的双人沙发，扶手上有一个烟头烫过的痕迹。

沙发旁边是一张小桌椅。桌上什么都没有。

然后你意识到了一个问题。一个相当大的问题。

这节车厢没有门。

? [逻辑推导 简单:7] 冷静地分析这个空间的结构。 → 成功:analyze_room_success | 失败:analyze_room_fail
? 「没有门？」你大声说了出来。 → call_out

---

## analyze_room_success
### 逻辑推导
等一下。一列火车上出现一个没有门的隔间，在物理上是不可能的。这意味着两种情况之一：

一、门存在，只是被藏起来了。墙板可能有接缝，沙发可能挡住了一个推拉门。

二、这个隔间不是为"进入"设计的。它是为"困住"而造的。

两种可能性都不让人舒服。但第二种尤其不好。

另外——这节车厢在火车中段。你刚才喊叫的时候，声音没有往走廊里传。这说明——墙体异常地厚。

→ ansel_appears

---

## analyze_room_fail
### 逻辑推导
你试图清点这个空间的信息，但脑子里一片雾，什么都抓不住。你只知道：你在这里，没有门，窗外是灰的，墙在震。

这四件事放一块儿，等于一个意思——你被关起来了。至于为什么、被谁、怎么做到的，你暂时没有力气去想。

→ ansel_appears

---

## ansel_appears
### 旁白
墙壁的另一侧传来一阵窸窣声，然后是一个年轻女人的声音。带着一点不耐烦，但更多的是好奇。

→ ansel_appears_voice

---

## ansel_appears_voice
### ???
「——听到了。听到了听到了。」

「你是哪一站上来的？我怎么没在K城见过你？」

→ ansel_appears_pause

---

## ansel_appears_pause
### 旁白
短暂的沉默。

→ ansel_appears_question

---

## ansel_appears_question
### ???
「……等一下。你的声音是从哪传出来的？」

? 「我不知道。我醒来就在这里。」 → ansel_confused
? 「先告诉我——这列火车是去哪的？」 → ansel_explain_train
? [哲学思辨 困难:11] 「……也许我根本就没'上来'过。」 → 成功:ansel_philosophical | 失败:ansel_confused

---

## ansel_confused
### 逻辑推导
墙上传来手指敲击的声音。三下，指节，间隔均匀。她不是在随意地碰——她在测试墙的厚度，在确认你的位置。这说明你和她之间的障碍是物理的，不是心理的。她需要先理解这堵墙，才能决定怎么对待墙后的人。

→ ansel_confused_voice

---

## ansel_confused_voice
### Ansel
「嗯……这堵墙后面没有车厢啊。我这边是走廊。你那边——」

→ ansel_confused_pause

---

## ansel_confused_pause
### 旁白
她顿了一下。

→ ansel_confused_air

---

## ansel_confused_air
### Ansel
「你那边按理说什么都不该有。这是两节车厢之间的连接处。理论上，你站的地方应该是……空气。」

→ ansel_intro

---

## ansel_explain_train
### 灵魂叙事
她的声音稍微认真了一些。之前她的声调是上扬的——好奇，轻快，像在解一道有趣的谜。现在往下沉了半度。一个愿意跟你讲空海是什么的人，和一个愿意跟你讲铁轨是什么的人，是两种不同的认真。

→ ansel_explain_train_voice

---

## ansel_explain_train_voice
### Ansel
「哦——好的，对，你应该不太清楚——」

「这趟列车是从K城开往A城的。诺斯塔吉亚号。人类在这个狗屁世界里仅存的两座城市之间，第一条铁轨。空海之后的第一条。你听懂了吗？空海——那个把世界吃掉的雾。已经三十多年了。」

→ ansel_intro

---

## ansel_philosophical
### 哲学思辨
你脱口而出的话让你自己都吃了一惊。随即你意识到——这不是随便说的。

如果你没有记忆，那你凭什么断定自己"上了"这列火车？也许你一开始就在墙上。也许你就是这节车厢。也许你是被某种东西——

好了。打住。哲学思辨在这样的时候通常帮不了你。

→ ansel_intro

---

## ansel_intro
### Ansel
「总之——我叫Ansel。K城的人。你是……」

→ ansel_intro_wait

---

## ansel_intro_wait
### 旁白
她等着你说名字。

你没有说话。

不是不想说。是你突然意识到——你不知道自己叫什么。

这是种奇怪的感觉。一个词就在嘴边，一个这辈子你用过最多次的词，但你找不到它。它不在那里。

? 「我……我不知道我叫什么。」 → forgot_name
? 努力回想。 → try_remember_name
? 随便编个名字。 → make_up_name

---

## forgot_name
### 缪斯女神
长久的沉默。沉默是一种特殊的声音——它把周围的嗡鸣、呼吸、墙壁的震动都变成了乐器。在这段空白里，Ansel正在重新排列她脑子里关于你的所有碎片。安静是创造的前奏。她快要写出第一行了。

→ forgot_name_voice

---

## forgot_name_voice
### Ansel
「……你不记得自己的名字。」

→ forgot_name_beat

---

## forgot_name_beat
### 逻辑推导
这不是问句。没有升调，没有疑问词，不需要你的确认。Ansel说"你不记得自己的名字"的方式，和她说"这堵墙后面没有车厢"是一样的——陈述事实。她已经在调整自己的认知模型了。

→ forgot_name_ok

---

## forgot_name_ok
### Ansel
「好吧。」

→ forgot_name_soft

---

## forgot_name_soft
### 灵魂叙事
她的声音突然变得很轻，像是在对自己说话。不是对你说"好吧"，是对她自己。你听出来了——她不是在敷衍你，她是在消化。一个人消化一件不可能的事情时，声音会先塌下来。

→ forgot_name_ok2

---

## forgot_name_ok2
### Ansel
「好吧。」

→ name_input

---

## try_remember_name
### 旁白
你闭上眼睛。

名字。名字。

你试图在空白的记忆里翻找，像在一个被清空的抽屉里摸索。手指碰到了一些碎片——

一个人影。一扇窗户。夏天。汗湿的衬衫贴在背上的感觉。

一个数字：503。

没有名字。

你睁开眼。

→ name_input

---

## make_up_name
### 缪斯女神
名字。名字是诗歌的开头。是所有故事的第一个词。

所以你为什么不给自己一个故事的开头呢？

一个音节，一个笔划，一个能在这堵墙之间站住脚的词——那就是你了。至少现在是你。

→ name_input

---

## name_input
### Ansel
「没关系。慢慢想。如果实在想不起来——」

→ name_input_beat

---

## name_input_beat
### 逻辑推导
她停了停。墙那边传来什么东西被翻开的声音——纸页的摩擦，然后是某种硬壳封面合上的脆响。也许是一本乘客名册。也许只是一本她自己带的笔记。无论如何，她正在用她能找到的工具来应对一个无法归类的情况。

→ name_input_prompt

---

## name_input_prompt
### Ansel
「你就告诉我，你想让我怎么叫你。」

? 输入你的名字。 → ansel_questions @inputName

---

## ansel_questions
### Ansel
「{playerName}。」

→ ansel_questions_beat

---

## ansel_questions_beat
### 灵魂叙事
她念了一遍，像是在品尝这个词的重量。

然后她沉默了几秒。当她再开口的时候，语调变了——不再是好奇，是某种谨慎。

→ ansel_questions_probe

---

## ansel_questions_probe
### Ansel
「你说你醒来就在里面。没有门。没有记忆。」

→ ansel_questions_knock

---

## ansel_questions_knock
### 逻辑推导
她的手指在墙上敲了两下。和刚才不同——节奏慢了一倍，力度更轻。这不是试探墙的厚度，这是人在思考时的无意识动作。她正在把关于你的碎片拼成一幅图。但这幅图的边缘还缺了几块。她知道，她也知道你知道。

→ ansel_questions_challenge

---

## ansel_questions_challenge
### Ansel
「你怎么证明你不是自己走进去然后把门封上的？」

→ ansel_questions_silence

---

## ansel_questions_silence
### 旁白
你没有回答。你没法回答。

→ ansel_questions_anything

---

## ansel_questions_anything
### Ansel
「你有任何东西吗？一个名字、一个地方、一个人——任何能证明你是谁的东西？」

→ ansel_questions_silence2

---

## ansel_questions_silence2
### 灵魂叙事
还是沉默。你开始理解墙那边的安静了——它不是空的。它在呼吸。墙那边传来一声轻轻的响动，不是叹气，比叹气更轻、更短。是某种确认。像一个侦探在档案上画了一个圈。她证实了一个她不太喜欢的猜想。现在她知道了，而你还没从她嘴里听到结论，但你已经从沉默里听到了。

→ ansel_questions_verdict

---

## ansel_questions_verdict
### Ansel
「……这不对劲。你不是在装。你是真的什么都没有。」

→ ansel_talk_hub

---

## ansel_talk_hub
### Ansel
「在我去找副列车长之前——你还有什么想问的吗？虽然我也不确定我能回答多少。」

? 「这列火车……它安全吗？」 → hub_train_safe &loop
? 「你说你是K城的人——那里是什么样的？」 → hub_kcity &loop
? 「墙那边的走廊，是什么样子的？」 → hub_corridor &loop
? [逻辑推导 中等:9] 仔细听Ansel的声音——她是不是在隐瞒什么？ → 成功:hub_ansel_doubt_ok | 失败:hub_ansel_doubt_fail &loop
? 「没事了，去找副列车长吧。」 → ansel_goes_for_ezra

---

## hub_train_safe
### Ansel
「安全？这是诺斯塔吉亚号的第一次正式运行。第一条跨空海铁轨。说实话，没人能在这条线上给你保证'安全'两个字怎么写。」

→ hub_train_safe_knock

---

## hub_train_safe_knock
### 旁白
她敲了敲墙壁。

→ hub_train_safe_extra

---

## hub_train_safe_extra
### Ansel
「虽然说实话，你这节车厢不在任何结构图上……这让我有点不确定'安全'两个字该怎么写。」

→ &return

---

## hub_kcity
### Ansel
「K城——怎么说呢。空海之后仅剩的两座城市之一。不大。旧城区的楼都不高，外墙是八十年代的白色瓷砖，阴天的时候看起来像一块巨大的肥皂。」

→ hub_kcity_beat

---

## hub_kcity_beat
### 旁白
她停了一下。

→ hub_kcity_pity

---

## hub_kcity_pity
### Ansel
「你连K城都不记得了？……算了。当我没问。」

→ &return

---

## hub_corridor
### Ansel
「就是普通的列车走廊。窄。灯光是黄的。墙上有铆钉，地上铺着那种被踩了太多次的地毯——灰绿色的，或者曾经是灰绿色的。」

→ hub_corridor_beat

---

## hub_corridor_beat
### 旁白
她顿了顿。

→ hub_corridor_door

---

## hub_corridor_door
### Ansel
「跟你那边差不多，只不过我这边有门。你真的没有门？一扇都没有？」

→ &return

---

## hub_ansel_doubt_ok
### 逻辑推导
你说完这句话之后，Ansel沉默了一瞬——比正常的停顿短了大概半秒。

她的声音里有某种东西。不是撒谎——撒谎的人会用更多词。她用的是更少的词。她在省略什么。

也许不是她不想告诉你。也许是你这节没有门的车厢，让"全部真相"这个词变得不太适用。

→ &return

---

## hub_ansel_doubt_fail
### 逻辑推导
你试图从她的声调、节奏、换气的间隙里提取信息。但隔着这堵墙，声音就像蒙了一层布。你什么都抓不住。

也许她确实在隐瞒什么。也许没有。你无法判断。

→ &return

---

## ansel_goes_for_ezra
### Ansel
「你等着。我去找副列车长。他姓——算了这不重要。他在铁路上干了很多年，他知道的事比我多。」

→ ansel_goes_beat

---

## ansel_goes_beat
### 旁白
她顿了顿。

→ ansel_goes_warn

---

## ansel_goes_warn
### Ansel
「别乱动。也别——别敲墙。墙很厚，你敲了也没人听得见。我很快就回来。」

→ ansel_goes_footsteps

---

## ansel_goes_footsteps
### 技术专家
脚步声——频率约每分钟一百二十步，步幅偏短，重心落在前脚掌。Ansel的步态说明两件事：她习惯在移动的列车上走路，而且她现在急着去找人。脚步声很快被走廊尽头的嗡鸣吞没了。在隔音如此差的车厢里，你能追踪一个人从站定到完全消失的精确时长：大约十二秒。

→ waiting_moment

---

## waiting_moment
### 旁白
Ansel的脚步声沿着走廊远去。

车厢重新安静下来。不，不是安静——是只剩下那种低沉的嗡鸣。窗外的灰雾缓慢地翻涌着，像某种在睡眠中呼吸的巨大生物。

你一个人。

你有一个名字。但没有记忆。没有门。没有——任何东西。

桌上有一片白色药片。你没注意它是从哪儿来的。也许一直在那里。

它散发着一种淡淡的、干净的苦味。

? 拿起白色药片查看。 → examine_pill
? [缪斯女神 中等:9] 这颗药片让你想起了一首诗——你确定你读过。 → 成功:pill_poem | 失败:pill_blank
? 不吃。继续等。 → ezra_arrives

---

## examine_pill
### 旁白
一片普通的白色药片。比阿司匹林大一点，比安眠药小一点。

标签纸有一半被撕掉了，剩下几个模糊的字迹："……安……"

反面还有一行钢笔写的字，小得几乎看不清："不够的话来找我。"

你不知道这是什么药。但你的手指把它翻来覆去的样子——很熟练。你吃过这种药。或者给什么人吃过。

? 服用白色药片。 → take_pill
? 把药片收起来。 → save_pill @addItem:white_pill

---

## pill_poem
### 缪斯女神
白色。圆形的白。

它让你想起——

"我有一枚白色的药片/在衣兜里放了一整个春天/它慢慢溶化/变成我的指纹/每次我想起自己是谁/就舔一舔手指/——然后忘记。"

你确定你读过这首诗。一个年轻的女诗人写的。你甚至记得——封面上有一个手绘的窗台。

但你记不起那个诗人的名字了。

→ examine_pill

---

## pill_blank
### 缪斯女神
一片药。什么都不是。只是一片药。

你的缪斯好像不在家。

→ examine_pill

---

## take_pill
### 旁白
你把药片放进嘴里。没有水，干咽下去的时候喉咙发紧。

几秒后——不是晕眩，是清醒。像是有人把调焦环拧了一下。你脑子里的雾淡了一层。

这东西有用。

→ ezra_arrives @sanity:+1

---

## save_pill
### 旁白
你把药片放进衣兜里。

也许会有更需要它的时候。

→ ezra_arrives

---

## ezra_arrives
### 旁白
脚步声——两个人的。一个轻、快，一个沉稳、有节奏。

→ ezra_arrives_ansel

---

## ezra_arrives_ansel
### Ansel
「就是这里。」

→ ezra_arrives_ezra_intro

---

## ezra_arrives_ezra_intro
### 旁白
然后是另一个声音。男的。中年。低沉但是不沉重。像是把很多话在肚子里过了一遍才放出来。

→ ezra_arrives_ezra

---

## ezra_arrives_ezra
### Ezra
「你好。我是Ezra，本次列车的副列车长。Ansel跟我说了你的情况。」

→ ezra_arrives_pause

---

## ezra_arrives_pause
### 旁白
他停顿了一下。

→ ezra_arrives_questions

---

## ezra_arrives_questions
### Ezra
「我先问你几个问题。姓名？」

→ ezra_dont_know

---

## ezra_dont_know
### 旁白
你不知道。

→ ezra_arrives_age

---

## ezra_arrives_age
### Ezra
「年龄？」

→ ezra_dont_know2

---

## ezra_dont_know2
### 旁白
你不知道。

→ ezra_arrives_where

---

## ezra_arrives_where
### Ezra
「从哪里上车？」

→ ezra_dont_know3

---

## ezra_dont_know3
### 旁白
你不知道。

Ezra沉默了一阵。你听到他深吸了一口气。

→ ezra_arrives_verdict

---

## ezra_arrives_verdict
### Ezra
「你说你在一节没有门的车厢里。墙的另一侧是走廊——我的走廊。我在空海边缘跑了二十年的车——补给线、救援线——各种各样的铁轨都跑过。但这列火车，这条跨空海铁轨……是新的。全新的。结构图上从来没有你这节车厢。」

→ ezra_arrives_tone

---

## ezra_arrives_tone
### 灵魂叙事
他的语气很平。不是指责，不是审问。他说话的方式像一个已经见过太多怪事的人——怪事本身不让他惊讶，他惊讶的是自己居然还没学会习惯。这种语气里有一种疲惫的诚实。你可以信任一个用这种语气说话的人。

→ ezra_arrives_not_exist

---

## ezra_arrives_not_exist
### Ezra
「你不存在于这列火车上。」

? 「我知道这听起来不可能。但我在这里。」 → ezra_interrogation
? [逻辑推导 中等:9] Ezra的逻辑是严密的——但他的声音不太对。 → 成功:ezra_logic_success | 失败:ezra_interrogation

---

## ezra_interrogation
### Ezra
「我理解。」

→ ezra_interrogation_beat

---

## ezra_interrogation_beat
### 旁白
他的声音慢了下来。

→ ezra_interrogation_continue

---

## ezra_interrogation_continue
### Ezra
「我理解你说的是实话——至少你觉得是。」

→ ezra_interrogation_move

---

## ezra_interrogation_move
### 身强体壮
你听到他靠近墙壁。衣料摩擦金属表面——棉布和铆钉，发出一种干燥的、沙沙的声响。他把一只手撑在了墙上。不是拳头，是手掌。你的皮肤甚至能感觉到那个位置传来的微弱震动。他想离你近一点。物理上的近。一个老铁路人的习惯——靠近问题才能判断它有多重。

→ ezra_interrogation_duty

---

## ezra_interrogation_duty
### Ezra
「但你需要理解我的立场。我是一列火车上的副列车长。我的职责是确保车上的每一个人——以及每一项存在——不构成威胁。而你——请别介意——你不存在于任何乘客名单上。你不存在于任何结构图上。你不存在于任何我能查到的记录里。」

→ ezra_interrogation_ansel

---

## ezra_interrogation_ansel
### Ansel
「但他确实在说话。他不是鬼，Ezra。」

→ ezra_interrogation_ezra

---

## ezra_interrogation_ezra
### Ezra
「我知道。这就是问题。鬼倒好办了。」

→ ezra_relents

---

## ezra_logic_success
### 逻辑推导
等一下。

Ezra说这些话的时候——"你不存在于这列火车上"——他的语气不是质疑。不是审问。

是辩护。他是在为一个他自己也无法相信的事实辩护。

你察觉到了。他不是在对你说这些话。他是在说服他自己。

而这个发现比他的审问更让你不安。因为这意味着——他遇到过类似的事。

→ ezra_relents

---

## ezra_relents
### 身强体壮
长出一口气。你能听到气流从鼻腔和嘴唇之间挤过的声音——不是叹气，是释放。一个人的横膈膜在做了一个漫长的决定之后终于松开了。这口气里有二十年的铁轨、空海边缘的风、以及一个他以为自己不会再听到的声音。

→ ezra_relents_voice

---

## ezra_relents_voice
### Ezra
「你的声音——我听过。」

→ ezra_relents_beat

---

## ezra_relents_beat
### 缪斯女神
这句话像一颗石头掉进水里。不是砸进去的，是松手让它沉下去的。Ezra等了很久才说这句话——你能从水面上的涟漪看出来。它荡开的不是水花，是时间。水面之下，那个二楼窗户里的年轻人，那些夏天的老歌，那棵银杏树——都在波纹里慢慢显形。

→ ezra_relents_memory

---

## ezra_relents_memory
### Ezra
「不是最近。是以前。A城。旧城区。东风路那栋公寓。夏天的晚上，窗户都开着，因为热。我每天收工回家都会听到二楼有人在放音乐。老歌。翻来覆去就那几首。」

→ ezra_relents_slow

---

## ezra_relents_slow
### 旁白
他的声音慢了下来。

→ ezra_relents_confess

---

## ezra_relents_confess
### Ezra
「我从来没有见过那个人。但我记得那个声音。过了这么多年——我还是记得。」

→ ezra_relents_knock

---

## ezra_relents_knock
### 旁白
他的手指在墙上轻轻叩了一下。

→ ezra_relents_match

---

## ezra_relents_match
### Ezra
「你的声音和他一模一样。」

? 「那栋公寓楼——说下去。」 → ezra_apartment
? 「然后呢？」 → ezra_apartment
? [灵魂叙事 中等:9] 仔细听Ezra的回忆——他形容的不像一个陌生人。 → 成功:ezra_feel_success | 失败:ezra_apartment

---

## ezra_feel_success
### 灵魂叙事
Ezra形容的不是一个陌生人。

那是每天收工回家都能听到的声音。是他生活中固定的一部分——那个二楼的窗户，那些老歌，那个他从来没见过的年轻人。

他不知道为什么这个声音对他很重要。但你知道。你听出来了。

他需要那个声音继续存在。

因为在这个一切都在被空海吞噬的世界里，有一些东西——哪怕只是一个从来没见过的年轻人的声音——必须留下来。

→ ezra_apartment

---

## ezra_apartment
### Ezra
「A城。旧城区。东风路——不对，空海之后改名了，现在叫——算了这不重要。」

→ ezra_apartment_fast

---

## ezra_apartment_fast
### 逻辑推导
他说话的速度突然加快了。从之前的平缓节奏跳到了某种更急促的频率——句与句之间的间隔消失了。这不是正常的回忆，这是在翻箱倒柜。Ezra的脑子里有一个储物间，他正在把积压多年的细节一件一件扔出来，因为他怕漏掉什么重要的。人在回忆一个从未谋面的人时，语速和回忆老友时完全不同——前者更快，因为记忆太少了，怕说不完就没了。

→ ezra_apartment_detail

---

## ezra_apartment_detail
### Ezra
「那栋公寓楼不大。六层。没有电梯。外墙是那种八十年代的白色瓷砖，阴天的时候看起来像一块巨大的肥皂。水压不好，四楼以上夏天经常停水。门口有一棵银杏树，秋天的时候——」

→ ezra_apartment_stop

---

## ezra_apartment_stop
### 灵魂叙事
他突然停住了。话还没落就断了——不是句号，是破折号后面空白的那种断。他说得太投入了，忘了他面对的是一个不存在于任何名册上的人。这种戛然而止比任何句子都诚实：他不是在回忆一栋楼，他是在回忆一段生活。一段他从来没有理由对任何人说起的生活。

→ ezra_apartment_awkward

---

## ezra_apartment_awkward
### Ezra
「……我在跟你说这些干什么。你又不一定来自那栋楼。」

? 「说下去。那棵银杏树——」 → ezra_ginkgo
? 「503。」 → utter_503

---

## ezra_ginkgo
### 旁白
你说完这句话之后，Ezra沉默了整整五秒。

不是因为你说错了什么。是——你也不知道自己为什么能看到那棵树。但你看到了。就在你说出来的那个瞬间，你的脑子里浮现了一幅画面：

一棵银杏树。秋天的傍晚。金黄色的扇形叶子铺了一地。树下有个人站着，仰着头往楼上看。

你看不清那个人的脸。

但你在楼上。你在窗户里头。你在往下看。

→ utter_503

---

## utter_503
### 你
「503。」

→ utter_503_beat

---

## utter_503_beat
### 旁白
你说出这三个数字的时候，声音很轻。轻得几乎像叹一口气。

但墙那边突然没了声音。

→ utter_503_ansel

---

## utter_503_ansel
### Ansel
「什么？你说什么？」

→ utter_503_ezra

---

## utter_503_ezra
### 旁白
然后是Ezra。他的语调完全变了——变得警觉。不是害怕。是警觉。

→ utter_503_ezra_voice

---

## utter_503_ezra_voice
### Ezra
「——你刚才说什么？」

? 「503。我知道这个数字。」 → ezra_reacts_to_503
? 「没什么。就是脑子里冒出来的。」 → ezra_reacts_to_503

---

## ezra_reacts_to_503
### 身强体壮
长久的沉默。然后你听到Ezra后退了一步——鞋底和金属地板之间短暂的摩擦声，接着是脚跟在另一块板上落定的闷响。不是随意的一步。是一个人听到了某个不该存在的数字之后，本能地往后让开。他的身体比他的脑子更快地理解了"503"意味着什么。

→ ezra_reacts_ezra

---

## ezra_reacts_ezra
### Ezra
「Ansel。你在这里等着。我去叫两个人。」

→ ezra_reacts_ansel

---

## ezra_reacts_ansel
### Ansel
「叫谁？」

→ ezra_reacts_ezra2

---

## ezra_reacts_ezra2
### Ezra
「老列车长——Conrad。还有——」

→ ezra_reacts_ezra_pause

---

## ezra_reacts_ezra_pause
### 哲学思辨
他停了一瞬。那一瞬里有东西——还没说出来的东西。

→ ezra_reacts_ezra_mystery

---

## ezra_reacts_ezra_mystery
### Ezra
「还有一个乘客。一位女士。她——你见了就知道了。」

→ ezra_reacts_ansel2

---

## ezra_reacts_ansel2
### Ansel
「她和这事有什么关系？」

→ ezra_reacts_ezra_leave

---

## ezra_reacts_ezra_leave
### 旁白
Ezra没有回答。他的脚步声已经走出了好几步。

→ ezra_reacts_ansel_last

---

## ezra_reacts_ansel_last
### Ansel
「{playerName}——你到底是谁？」

→ first_flash

---

## first_flash
### 旁白
你没有机会回答。

因为在等待的寂静中，突然——不是画面，不是声音。是**触感**。

你的手指上——湿的。温热的。粘稠的。

你低头看自己的手。干净的。什么都没有。

但那感觉不肯退。它贴在你的指腹上，像是浸透了皮肤。你把手翻过来——掌纹。生命线。干干净净。

然后一个声音碎片——短到几乎不存在——女人的声音。在笑。然后不笑了。

太短了。抓不住。

但你的心跳快了半拍。

→ train_shakes

---

## train_shakes
### 旁白
你没有时间思考那个触感意味着什么。

因为就在下一秒——

整列火车猛地一震。

不是刹车。不是转弯。是从轨道深处涌上来的一股力量——像是有什么巨大的东西从地底推了铁轨一把。

车厢里的灯疯狂地晃了两下。桌上的东西滑到了地上。

你试图抓住什么东西——墙、沙发、桌子——手指在金属上滑了一下——

后脑勺撞到了桌椅的边缘。

一声闷响。

→ train_shakes_ansel

---

## train_shakes_ansel
### Ansel
「{playerName}！{playerName}！」

→ train_shakes_fade

---

## train_shakes_fade
### 旁白
她的声音很远——像是在一个长长的走廊那头。

世界在往后退。

你的意识变成了一条狭长的缝。在缝隙合拢之前，你看到了最后一幅画面——

一棵银杏树。秋天的傍晚。满地金黄的叶子。

树下有一个人。

这次你看清了他的脸。

那是一个穿深色外套的年轻人——很瘦。他在仰头看二楼的窗户。窗户开着。窗帘被风吹起来。

你认出了他。

不——你认出了那个窗户里的视角。

那是你自己。从窗户里往下看。看着树下的人。

缝隙合拢。

一切归于黑暗。

→ demo_end

---

## demo_end
### 旁白
你浮在黑暗里。

但黑暗不是终点——它只是一扇尚未打开的门。

那些碎片——503号房间、银杏树、手指上血的触感、一个女人在笑然后不笑的声音——它们悬浮在黑暗中，像未拆的信。

Ansel还在墙那边吗？Ezra去找谁了？那个老列车长叫什么名字？那个等着儿子回家的女人——她还不知道她等的人已经不在了。

你也不知道。你只知道你在这里。在一节不存在的车厢里。在空海的正中央。

而你还没有死。

**—— 第一章 Demo 完 ——**

感谢试玩。

@end

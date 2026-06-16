@item white_pill
name: White Pill
desc: A white tablet with a faint grassy smell. Half the label is torn off. It smells calming — you don't know what it is, but you have a vague sense of what it does.
usable: true
effect: sanity_restore 1
consume: true
@enditem

@item faded_thread
name: Faded Thread
desc: A faded red thread, probably fallen from an old suit. Holding it in your hand feels reassuring — like holding someone's sleeve.
usable: true
effect: hp_restore 1
consume: true
@enditem

# 开场
@music: assets/灰雾_no-watermark.mp3

## wake_up
### Narrator
You wake up.

No — more precisely, you are waking up. You feel yourself floating on a boundary. On one side, deep-sea blackness, a void spinning and consuming all gaze. On the other, a grey-white milky space. Grey fish flicker past and are gone.

→ feeling_something_in_the_dark

---

## feeling_something_in_the_dark
### Narrator
Their touch tickles faintly. Something seems to be watching you. An icy cold crawls across your cerebral cortex, wailing like an infant. A damp, sticky liquid gathers at the crown of your empty skull, then drips. A trace of ozone. A hint of fish. And a taste — the taste of electricity.

Laughter pulls up the stars of the universe in the distance. A curtain called life is about to be stitched together from this.

? Wait, what does electricity taste like? → electric_feel
? This is terrifying. I don't want to wake up. → do_not_wake_up1

---
## electric_feel
### Narrator
The hospitals of this world welcome fifty to sixty thousand newborns every day. Most arrive under the flickering lights of operating rooms. Outside the door, red turns to green; inside, faces between currents show relief. Some nurses gently pat the baby's back to make the silent ones cry.

From artificial electricity to bioelectricity — so some say electricity tastes like protein. But that might just be the shock.

? [Soul Narrative Simple:5] Did I just hear dice? → 成功:first_try_success | 失败:first_try_fail
? Enough. Stop thinking. I'm waking up. → first_look

---

## do_not_wake_up1
### Narrator
The dark water carries a faint rust smell. A gun has melted in front of you.

Melted: not from rising temperature, but from the disappearance of temperature as a concept. You sense that your yet-unformed hearing and vision are leaving you too. You will no longer see those figures. The dice are still rolling, but you can no longer hear them.

? [Soul Narrative Simple:5] Aren't the dice still there? Give it a try. → 成功:first_try_success | 失败:first_try_fail
? Forget it. Let it end. → do_not_wake_up2

---

## first_try_success
### Narrator
Yes! That's it! The sound of dice! That maddening, enchanting sound!

Come — entrust your life to the dice once more. Pull yourself from that wet darkness!

? I want to wake up. → first_look
? That's enough. Good night. → do_not_wake_up2

---

## first_try_fail
### Narrator
No dice. An illusion. A kaleidoscopic hallucination.

The old building walls are covered in ivy. At dusk, the city's brick walls are reddest. In the shadows beneath the leaves, something is always watching you. But you can no longer see even this.

→ do_not_wake_up2

---

## do_not_wake_up2
### Narrator
You curl up — if you can control your limbs.
You stay silent — if you can control your breath.
You sleep — if you can still hold consciousness.

The grey fish return. Soft grey. Each fish is a finger of a larger being. This thousand-finger hand climbs onto your non-existent body, wraps around you, caresses you.

And then, from the long history of humankind, you hear a terrible gunshot.

@end

---
@bg: assets/bg_开场.png
@music: assets/轨道_no-watermark.mp3
@volume: 0.2

## first_look
### Narrator
You open your eyes.

The ceiling is low. Rivets. Metal plates joined together. A dim yellow light sways rhythmically — like being underwater.

You hear a low, steady hum. Not tinnitus. It comes from inside the walls.

→ stand_up

---

## stand_up
### Narrator
You try to stand. Your legs are weak — not from exhaustion, but from a more fundamental strangeness. As if these muscles aren't yours. As if you haven't settled into whatever relationship you have with this body yet.

You brace against the wall. It's vibrating.

? Look around. → look_around
? "Anyone there?" → call_out

---

## look_around
### Narrator
It's a train compartment.

But something is off. One side has a window — rectangular, coated with grey dust on the outside. You move closer and wipe the glass with your hand.

The grey is outside.

The inside of the glass is clean. That grey — or not-grey — clings evenly to the other side of the glass, like fog, but more... solid. It flows and it freezes. It's like gas and like fabric. You stare at it for a few seconds. A nameless unease settles in — not because it's frightening, but because it reminds you of something. You just can't remember what.

→ try_window

---

## try_window
### Narrator
You try the window. It's locked. Or maybe there's no lock at all — it looks welded shut. You tap the glass with your knuckle. The sound is dull, like knocking on waterlogged wood.

The grey thing outside doesn't react. Of course it doesn't react. It's not alive.

...Right?

→ notice_no_door

---

## call_out
### You
"Hello — is anyone there —"

→ voice_responds

---

## voice_responds
### Narrator
Your voice bounces twice in the compartment and dies. The compartment is too small — the size of a booth — to hold an echo.

But then you hear something.

From the other side of the wall. Not an echo. A human voice.

→ ansel_appears

---

## notice_no_door
### Narrator
You turn, scanning the four walls.

The wall with the window.

Opposite it: a sofa — old, cracked leather, with a cigarette burn on one armrest.

Beside the sofa: a small table and chair. Nothing on the table.

And then you realize something. Something fairly significant.

This compartment has no door.

? [Logical Deduction Easy:7] Calmly analyze the structure of this space. → 成功:analyze_room_success | 失败:analyze_room_fail
? "No door?" you say out loud. → call_out

---

## analyze_room_success
### Logical Deduction
Wait. A doorless compartment on a moving train is physically impossible. Which means one of two things:

One: the door exists but is hidden. Wall panels may have seams. The sofa might be blocking a sliding door.

Two: this compartment wasn't designed for entry. It was designed for containment.

Neither possibility is comforting. The second one is significantly worse.

Also — this compartment is in the middle of the train. When you shouted, the sound didn't carry into the corridor. That means — the walls are abnormally thick.

→ ansel_appears

---

## analyze_room_fail
### Logical Deduction
You try to inventory the information in this space, but your mind is fog. Nothing sticks. All you know: you're here, there's no door, the window shows grey, and the walls vibrate.

These four facts add up to one thing — you're trapped. As for why, by whom, or how — you don't have the energy to figure that out right now.

→ ansel_appears

---

## ansel_appears
### Narrator
A rustling sound from the other side of the wall. Then a young woman's voice — a little impatient, but mostly curious.

→ ansel_appears_voice

---

## ansel_appears_voice
### ???
"—I heard you. Heard you, heard you."

"Which station did you board at? I don't remember seeing you in K-City."

→ ansel_appears_pause

---

## ansel_appears_pause
### Narrator
A brief silence.

→ ansel_appears_question

---

## ansel_appears_question
### ???
"...Wait. Where is your voice coming from?"

? "I don't know. I woke up here." → ansel_confused
? "First tell me — where is this train going?" → ansel_explain_train
? [Philosophical Thought Hard:11] "...Maybe I never 'boarded' at all." → 成功:ansel_philosophical | 失败:ansel_confused

---

## ansel_confused
### Logical Deduction
The sound of fingers tapping against the wall. Three taps, knuckles, evenly spaced. She's not touching the wall casually — she's testing its thickness, confirming your position. This means the barrier between you is physical, not psychological. She needs to understand the wall before she decides what to do with the person behind it.

→ ansel_confused_voice

---

## ansel_confused_voice
### Ansel
"Hmm... there's no compartment behind this wall. This side is the corridor. Your side —"

→ ansel_confused_pause

---

## ansel_confused_pause
### Narrator
She pauses.

→ ansel_confused_air

---

## ansel_confused_air
### Ansel
"Your side should be nothing. This is the junction between two cars. Theoretically, where you're standing should be... air."

→ ansel_intro

---

## ansel_explain_train
### Soul Narrative
Her voice turns slightly more serious. Before, her tone was lifted — curious, light, like solving an interesting puzzle. Now it's dropped half a step. There's a difference between someone who's willing to tell you what the Void Sea is, and someone who's willing to tell you what the rails are.

→ ansel_explain_train_voice

---

## ansel_explain_train_voice
### Ansel
"Oh — right, okay, you probably don't know —"

"This train runs from K-City to A-City. The Nostalgia. Humanity's first rail line between the only two cities left in this godforsaken world. The first one after the Void Sea. Do you understand? The Void Sea — that fog that ate the world. It's been over thirty years."

→ ansel_intro

---

## ansel_philosophical
### Philosophical Thought
The words escape your mouth before you can stop them. And then you realize — you didn't say it casually.

If you have no memory, what makes you so sure you "boarded" this train? Maybe you were always in the walls. Maybe you ARE the compartment. Maybe you're something that —

Alright. Stop. Philosophy usually doesn't help at times like this.

→ ansel_intro

---

## ansel_intro
### Ansel
"Anyway — I'm Ansel. From K-City. And you are..."

→ ansel_intro_wait

---

## ansel_intro_wait
### Narrator
She waits for a name.

You say nothing.

Not because you don't want to. Because you've just realized — you don't know your name.

It's a strange feeling. A word on the tip of your tongue, the word you've used more than any other in your life, but you can't find it. It isn't there.

? "I... I don't know my name." → forgot_name
? Try hard to remember. → try_remember_name
? Make up a name. → make_up_name

---

## forgot_name
### The Muse
A long silence. Silence is a peculiar kind of sound — it turns the hum, the breathing, the vibration of the walls into instruments. In this gap, Ansel is rearranging every fragment she has about you. Quiet is the prelude to creation. She's about to write the first line.

→ forgot_name_voice

---

## forgot_name_voice
### Ansel
"...You don't remember your own name."

→ forgot_name_beat

---

## forgot_name_beat
### Logical Deduction
That wasn't a question. No rising intonation, no interrogative particle, no need for your confirmation. She said "you don't remember your name" the same way she said "there's no compartment behind this wall" — stating a fact. She's already adjusting her mental model.

→ forgot_name_ok

---

## forgot_name_ok
### Ansel
"Alright."

→ forgot_name_soft

---

## forgot_name_soft
### Soul Narrative
Her voice suddenly becomes very soft, as if talking to herself. She didn't say "alright" to you — she said it to herself. She's not dismissing you. She's digesting. When a person digests something impossible, their voice collapses first.

→ forgot_name_ok2

---

## forgot_name_ok2
### Ansel
"Alright."

→ name_input

---

## try_remember_name
### Narrator
You close your eyes.

Name. Name.

You fumble through the blankness of your memory like searching an emptied drawer. Your fingers brush against fragments —

A silhouette. A window. Summer. The feeling of a sweat-damp shirt clinging to your back.

A number: 503.

No name.

You open your eyes.

→ name_input

---

## make_up_name
### The Muse
A name. A name is the beginning of a poem. The first word of every story.

So why don't you give yourself the beginning of a story?

A syllable, a stroke, a word that can stand its ground between these walls — that's you. At least for now.

→ name_input

---

## name_input
### Ansel
"It's okay. Take your time. If you really can't remember —"

→ name_input_beat

---

## name_input_beat
### Logical Deduction
She pauses. The sound of something being flipped through on the other side — the friction of paper pages, then the crisp snap of a hard cover closing. Maybe a passenger manifest. Maybe just a notebook of her own. Either way, she's reaching for whatever tools she has to deal with an unclassifiable situation.

→ name_input_prompt

---

## name_input_prompt
### Ansel
"Just tell me what you want me to call you."

? Enter your name. → ansel_questions @inputName

---

## ansel_questions
### Ansel
"{playerName}."

→ ansel_questions_beat

---

## ansel_questions_beat
### Soul Narrative
She repeats it, as if tasting the weight of the word.

Then she's silent for a few seconds. When she speaks again, her tone has changed — no longer curious. Something more cautious. She's not solving a puzzle anymore. She's standing in front of one that might solve her back.

→ ansel_questions_probe

---

## ansel_questions_probe
### Ansel
"You say you woke up inside. No door. No memory."

→ ansel_questions_knock

---

## ansel_questions_knock
### Logical Deduction
Her fingers tap the wall twice. Different from before — slower rhythm, lighter force. Not testing the thickness. This is the unconscious movement of someone thinking. She's assembling the fragments of you into a picture. But the edges are missing a few pieces. She knows it. And she knows you know it.

→ ansel_questions_challenge

---

## ansel_questions_challenge
### Ansel
"How do you prove you didn't walk in there and seal the door yourself?"

→ ansel_questions_silence

---

## ansel_questions_silence
### Narrator
You don't answer. You can't.

→ ansel_questions_anything

---

## ansel_questions_anything
### Ansel
"Do you have anything? A name, a place, a person — anything that proves who you are?"

→ ansel_questions_silence2

---

## ansel_questions_silence2
### Soul Narrative
Still silence. You're beginning to understand the quiet on the other side of the wall — it's not empty. It's breathing. From the other side comes a soft sound — not a sigh, lighter than a sigh, shorter. Confirmation. Like a detective circling something on a file. She's just verified a hypothesis she didn't like. Now she knows. And you haven't heard the conclusion from her mouth yet, but you've already heard it from the silence.

→ ansel_questions_verdict

---

## ansel_questions_verdict
### Ansel
"...This isn't right. You're not faking. You really have nothing."

→ ansel_talk_hub

---

## ansel_talk_hub
### Ansel
"Before I go get the deputy conductor — is there anything else you want to ask? Though I'm not sure how much I can answer."

? "This train... is it safe?" → hub_train_safe &loop
? "You said you're from K-City — what's it like there?" → hub_kcity &loop
? "What does the corridor on your side look like?" → hub_corridor &loop
? [Logical Deduction Medium:9] Listen closely to Ansel's voice — is she hiding something? → 成功:hub_ansel_doubt_ok | 失败:hub_ansel_doubt_fail &loop
? "Nothing else. Go get the deputy conductor." → ansel_goes_for_ezra

---

## hub_train_safe
### Ansel
"Safe? This is the Nostalgia's first official run. The first cross-Void Sea rail line. Honestly, no one can guarantee you how to spell 'safe' on this train."

→ hub_train_safe_knock

---

## hub_train_safe_knock
### Narrator
She knocks on the wall.

→ hub_train_safe_extra

---

## hub_train_safe_extra
### Ansel
"Although honestly, your compartment isn't on any structural diagram... that makes me a little unsure how to spell 'safe'."

→ &return

---

## hub_kcity
### Ansel
"K-City — how do I put it. One of only two cities left after the Void Sea. Not big. The old district buildings aren't tall, with that eighties-style white tile exterior. On cloudy days it looks like a giant bar of soap."

→ hub_kcity_beat

---

## hub_kcity_beat
### Narrator
She pauses.

→ hub_kcity_pity

---

## hub_kcity_pity
### Ansel
"You don't even remember K-City? ...Never mind. Forget I asked."

→ &return

---

## hub_corridor
### Ansel
"Just a regular train corridor. Narrow. Yellow lights. Rivets on the walls, and that carpet that's been stepped on too many times — grey-green, or at least it used to be grey-green."

→ hub_corridor_beat

---

## hub_corridor_beat
### Narrator
She pauses.

→ hub_corridor_door

---

## hub_corridor_door
### Ansel
"Pretty much like your side, except I have a door. You really don't have a door? Not even one?"

→ &return

---

## hub_ansel_doubt_ok
### Logical Deduction
After you say this, Ansel is silent for a beat — about half a second shorter than a normal pause.

There's something in her voice. Not lying — liars use more words. She's using fewer. She's omitting something.

Maybe she doesn't want to hide it from you. Maybe your doorless compartment makes the phrase "the whole truth" a little impractical.

→ &return

---

## hub_ansel_doubt_fail
### Logical Deduction
You try to extract information from her tone, her rhythm, the gaps between breaths. But through this wall, the voice comes wrapped in cloth. You can't grasp anything.

Maybe she's hiding something. Maybe not. You can't tell.

→ &return

---

## ansel_goes_for_ezra
### Ansel
"Wait here. I'm getting the deputy conductor. His surname is — never mind, it doesn't matter. He's worked the railways for years. He knows more than I do."

→ ansel_goes_beat

---

## ansel_goes_beat
### Narrator
She pauses.

→ ansel_goes_warn

---

## ansel_goes_warn
### Ansel
"Don't move. And don't — don't knock on the wall. It's too thick, no one would hear you anyway. I'll be back soon."

→ ansel_goes_footsteps

---

## ansel_goes_footsteps
### Technical Expert
Footsteps — approximately one hundred twenty per minute, short stride, weight on the balls of the feet. Ansel's gait tells you two things: she's used to walking on a moving train, and she's in a hurry to find someone. The footsteps are soon swallowed by the hum at the end of the corridor. In a carriage this poorly soundproofed, you can track the exact duration of a person from standing still to complete disappearance: about twelve seconds.

→ waiting_moment

---

## waiting_moment
### Narrator
Ansel's footsteps fade down the corridor.

The compartment settles back into silence. No — not silence. Just that low hum remains. Outside the window, the grey fog churns slowly, like some enormous creature breathing in its sleep.

You're alone.

You have a name. But no memory. No door. No — anything.

There's a white pill on the table. You didn't notice where it came from. Maybe it was always there.

It gives off a faint, clean bitterness.

? Pick up the white pill and examine it. → examine_pill
? [The Muse Medium:9] This pill reminds you of a poem — you're certain you've read it. → 成功:pill_poem | 失败:pill_blank
? Don't take it. Keep waiting. → ezra_arrives

---

## examine_pill
### Narrator
An ordinary white tablet. Slightly larger than aspirin, slightly smaller than a sleeping pill.

Half the label is torn off, leaving a few blurred characters: "...An..."

On the back, a line of handwriting so small it's barely legible: "If it's not enough, come find me."

You don't know what this pill is. But the way your fingers turn it over — practiced. You've taken this medicine before. Or given it to someone.

? Take the white pill. → take_pill
? Put the pill away. → save_pill @addItem:white_pill

---

## pill_poem
### The Muse
White. Round white.

It reminds you of —

"I kept a white pill / in my pocket for an entire spring / it slowly dissolved / became my fingerprint / each time I remembered who I am / I licked my finger / — and forgot."

You're certain you've read this poem. Written by a young female poet. You even remember — the cover had a hand-drawn windowsill.

But you can't remember the poet's name.

→ examine_pill

---

## pill_blank
### The Muse
A pill. Nothing more. Just a pill.

Your muse appears to be out.

→ examine_pill

---

## take_pill
### Narrator
You put the pill in your mouth. No water. Your throat tightens as you swallow it dry.

A few seconds later — not dizziness. Clarity. As if someone turned the focus ring. The fog in your mind thins by a layer.

This thing works.

→ ezra_arrives @sanity:+1

---

## save_pill
### Narrator
You tuck the pill into your pocket.

Maybe you'll need it more later.

→ ezra_arrives

---

## ezra_arrives
### Narrator
Footsteps — two sets. One light and quick, one steady and rhythmic.

→ ezra_arrives_ansel

---

## ezra_arrives_ansel
### Ansel
"Right here."

→ ezra_arrives_ezra_intro

---

## ezra_arrives_ezra_intro
### Narrator
Then another voice. Male. Middle-aged. Low but not heavy. Like someone who's thought through a lot of words before letting them out.

→ ezra_arrives_ezra

---

## ezra_arrives_ezra
### Ezra
"Hello. I'm Ezra, deputy conductor of this train. Ansel told me about your situation."

→ ezra_arrives_pause

---

## ezra_arrives_pause
### Narrator
He pauses.

→ ezra_arrives_questions

---

## ezra_arrives_questions
### Ezra
"Let me ask you a few questions. Name?"

→ ezra_dont_know

---

## ezra_dont_know
### Narrator
You don't know.

→ ezra_arrives_age

---

## ezra_arrives_age
### Ezra
"Age?"

→ ezra_dont_know2

---

## ezra_dont_know2
### Narrator
You don't know.

→ ezra_arrives_where

---

## ezra_arrives_where
### Ezra
"Where did you board?"

→ ezra_dont_know3

---

## ezra_dont_know3
### Narrator
You don't know.

Ezra is silent for a moment. You hear him take a deep breath.

→ ezra_arrives_verdict

---

## ezra_arrives_verdict
### Ezra
"You say you're in a compartment with no door. On the other side of the wall is a corridor — my corridor. I've run the rails along the Void Sea for twenty years — supply lines, rescue lines — all kinds of tracks. But this train, this cross-Void Sea line... it's new. Brand new. Your compartment has never appeared on any structural diagram."

→ ezra_arrives_tone

---

## ezra_arrives_tone
### Soul Narrative
His tone is flat. Not accusatory. Not interrogating. He speaks like a man who's seen too many strange things — the strangeness no longer surprises him; what surprises him is that he still hasn't learned to get used to it. There's a tired honesty in that tone. You can trust a person who speaks like this.

→ ezra_arrives_not_exist

---

## ezra_arrives_not_exist
### Ezra
"You do not exist on this train."

? "I know this sounds impossible. But I'm here." → ezra_interrogation
? [Logical Deduction Medium:9] Ezra's logic is sound — but his voice carries something else. → 成功:ezra_logic_success | 失败:ezra_interrogation

---

## ezra_interrogation
### Ezra
"I understand."

→ ezra_interrogation_beat

---

## ezra_interrogation_beat
### Narrator
His voice slows.

→ ezra_interrogation_continue

---

## ezra_interrogation_continue
### Ezra
"I understand you're telling the truth — at least, what feels true to you."

→ ezra_interrogation_move

---

## ezra_interrogation_move
### Physical Might
You hear him move closer to the wall. The sound of fabric against metal — cotton and rivets, a dry, rustling friction. He's placed a hand against the wall. Not a fist — a palm. You can feel the faint vibration of it at that spot. He wants to be closer to you. Physically closer. An old railway man's habit — get near the problem before you judge how heavy it is.

→ ezra_interrogation_duty

---

## ezra_interrogation_duty
### Ezra
"But you need to understand my position. I'm the deputy conductor of a train. My job is to ensure that every person — and every presence — on board is not a threat. And you — no offense — you don't appear on any passenger manifest. You don't appear on any structural diagram. You don't appear in any record I can check."

→ ezra_interrogation_ansel

---

## ezra_interrogation_ansel
### Ansel
"But he's really talking. He's not a ghost, Ezra."

→ ezra_interrogation_ezra

---

## ezra_interrogation_ezra
### Ezra
"I know. That's the problem. A ghost would be easier."

→ ezra_relents

---

## ezra_logic_success
### Logical Deduction
Wait.

When Ezra said those words — "You do not exist on this train" — his tone wasn't questioning. It wasn't interrogation.

It was defense. He was defending himself against a fact he couldn't believe.

You catch it. He's not saying these things to you. He's trying to convince himself.

And this realization disturbs you more than his questioning. Because it means — he's encountered something like this before.

→ ezra_relents

---

## ezra_relents
### Physical Might
A long exhale. You can hear the air squeezing past his lips and nostrils — not a sigh, a release. A man's diaphragm finally letting go after a long decision. In that breath are twenty years of rails, the winds at the edge of the Void Sea, and a voice he thought he'd never hear again.

→ ezra_relents_voice

---

## ezra_relents_voice
### Ezra
"Your voice — I've heard it."

→ ezra_relents_beat

---

## ezra_relents_beat
### The Muse
The words drop like a stone into water. Not thrown — released, let go. Ezra waited a long time to say this — you can tell from the ripples on the surface. They spread not as splashes but as circles. And beneath the water, the young man in that second-floor window, the old songs of summer, the ginkgo tree — they're all slowly taking shape in the ripples.

→ ezra_relents_memory

---

## ezra_relents_memory
### Ezra
"Not recently. Before. A-City. The old district. That apartment building on Dongfeng Road. Summer nights, windows all open because of the heat. Every day when I got off work, I'd hear someone on the second floor playing music. Old songs. The same few, over and over."

→ ezra_relents_slow

---

## ezra_relents_slow
### Narrator
His voice slows.

→ ezra_relents_confess

---

## ezra_relents_confess
### Ezra
"I never saw the person. But I remember the voice. After all these years — I still remember."

→ ezra_relents_knock

---

## ezra_relents_knock
### Narrator
His finger taps softly against the wall.

→ ezra_relents_match

---

## ezra_relents_match
### Ezra
"Your voice is exactly the same."

? "That apartment building — go on." → ezra_apartment
? "And then?" → ezra_apartment
? [Soul Narrative Medium:9] Listen closely to Ezra's memory — he's not describing a stranger. → 成功:ezra_feel_success | 失败:ezra_apartment

---

## ezra_feel_success
### Soul Narrative
Ezra isn't describing a stranger.

It was the voice he heard every day coming home from work. A fixed part of his life — that second-floor window, those old songs, that young man he never saw.

He doesn't know why this voice matters to him. But you know. You can hear it.

He needs that voice to continue existing.

Because in this world where everything is being devoured by the Void Sea, some things — even just the voice of a young man he never met — must remain.

→ ezra_apartment

---

## ezra_apartment
### Ezra
"A-City. Old district. Dongfeng Road — no, they renamed it after the Void Sea, now it's called — never mind, it doesn't matter."

→ ezra_apartment_fast

---

## ezra_apartment_fast
### Logical Deduction
His speech suddenly accelerates. From the steady rhythm before, it jumps to a quicker frequency — the gaps between sentences vanish. This isn't normal recollection; it's rummaging. Ezra has a storage room in his mind, and he's throwing out details one by one, afraid he'll miss something important. When a person recalls someone they never met, their pace is nothing like recalling an old friend — it's faster, because there's too little memory, and they're afraid it'll run out before they finish.

→ ezra_apartment_detail

---

## ezra_apartment_detail
### Ezra
"The building wasn't big. Six floors. No elevator. The exterior was that eighties-style white tile — looked like a giant bar of soap on cloudy days. Bad water pressure, fourth floor and above lost water often in summer. There was a ginkgo tree at the entrance. In autumn —"

→ ezra_apartment_stop

---

## ezra_apartment_stop
### Soul Narrative
He stops abruptly. The words cut off before they land — not a period, the kind of break that comes after a dash into blank space. He was too absorbed, forgot he's talking to someone who doesn't exist on any manifest. This sudden silence is more honest than any sentence: he wasn't remembering a building. He was remembering a life. A life he's never had any reason to tell anyone about.

→ ezra_apartment_awkward

---

## ezra_apartment_awkward
### Ezra
"...Why am I telling you all this. You might not even be from that building."

? "Go on. The ginkgo tree —" → ezra_ginkgo
? "503." → utter_503

---

## ezra_ginkgo
### Narrator
After you say this, Ezra is silent for a full five seconds.

Not because you said something wrong. It's — you don't know how you can see that tree either. But you do. At the moment the words leave your mouth, an image surfaces in your mind:

A ginkgo tree. Autumn evening. Golden fan-shaped leaves covering the ground. Someone standing beneath it, looking up at the building.

You can't make out the person's face.

But you're upstairs. You're inside the window. Looking down.

→ utter_503

---

## utter_503
### You
"503."

→ utter_503_beat

---

## utter_503_beat
### Narrator
The three numbers come out very soft. Almost like a sigh.

But the other side of the wall goes suddenly silent.

→ utter_503_ansel

---

## utter_503_ansel
### Ansel
"What? What did you say?"

→ utter_503_ezra

---

## utter_503_ezra
### Narrator
Then Ezra. His tone has completely changed — alert. Not scared. Alert.

→ utter_503_ezra_voice

---

## utter_503_ezra_voice
### Ezra
"—What did you just say?"

? "503. I know this number." → ezra_reacts_to_503
? "Nothing. Just popped into my head." → ezra_reacts_to_503

---

## ezra_reacts_to_503
### Physical Might
A long silence. Then you hear Ezra take a step back — the brief friction of a shoe sole against the metal floor, then the dull thud of a heel landing on the next panel. Not a casual step. A person who's just heard a number that shouldn't exist, instinctively backing away. His body understood what "503" meant faster than his brain did.

→ ezra_reacts_ezra

---

## ezra_reacts_ezra
### Ezra
"Ansel. Wait here. I'm going to get two people."

→ ezra_reacts_ansel

---

## ezra_reacts_ansel
### Ansel
"Who?"

→ ezra_reacts_ezra2

---

## ezra_reacts_ezra2
### Ezra
"The old conductor — Conrad. And —"

→ ezra_reacts_ezra_pause

---

## ezra_reacts_ezra_pause
### Philosophical Thought
He stops for a beat. In that beat there's something — something still unspoken.

→ ezra_reacts_ezra_mystery

---

## ezra_reacts_ezra_mystery
### Ezra
"Another passenger. A lady. She — you'll understand when you meet her."

→ ezra_reacts_ansel2

---

## ezra_reacts_ansel2
### Ansel
"What does she have to do with this?"

→ ezra_reacts_ezra_leave

---

## ezra_reacts_ezra_leave
### Narrator
Ezra doesn't answer. His footsteps are already several paces away.

→ ezra_reacts_ansel_last

---

## ezra_reacts_ansel_last
### Ansel
"{playerName} — who ARE you?"

→ first_flash

---

## first_flash
### Narrator
You don't get a chance to answer.

Because in the waiting silence, suddenly — not an image, not a sound. A **sensation**.

Your fingers — wet. Warm. Sticky.

You look down at your hands. Clean. Nothing there.

But the feeling won't recede. It clings to your fingertips, as if soaked into the skin. You turn your hand over — palm lines. Life line. Perfectly clean.

Then a fragment of sound — so short it barely exists — a woman's voice. Laughing. Then not laughing.

Too short. You can't hold onto it.

But your heart beats half a beat faster.

→ train_shakes

---

## train_shakes
### Narrator
You have no time to process what that sensation means.

Because in the very next second —

The entire train lurches violently.

Not braking. Not a turn. A force surging up from deep within the tracks — as if something enormous pushed the rails from below.

The compartment light swings wildly. Objects slide off the table.

You try to grab something — wall, sofa, table — your fingers slip on metal —

The back of your head hits the edge of the table and chair.

A dull thud.

→ train_shakes_ansel

---

## train_shakes_ansel
### Ansel
"{playerName}! {playerName}!"

→ train_shakes_fade

---

## train_shakes_fade
### Narrator
Her voice is very far away — as if from the end of a long corridor.

The world recedes.

Your consciousness narrows to a thin slit. Before the slit closes, you see one last image —

A ginkgo tree. Autumn evening. Golden leaves covering the ground.

Someone stands beneath the tree.

This time you see his face clearly.

A young man in a dark coat — very thin. He's looking up at a second-floor window. The window is open. The curtain lifts in the wind.

You recognize him.

No — you recognize the view from the window.

It's yourself. Looking down from the window. Watching the person beneath the tree.

The slit closes.

Everything goes dark.

→ demo_end

---

## demo_end
### Narrator
You float in darkness.

But darkness is not the end — it is only a door not yet opened.

The fragments — Room 503, the ginkgo tree, the wet warmth on your fingers, a woman's voice laughing then not laughing — they hang in the dark like unopened letters.

Is Ansel still on the other side of the wall? Who was Ezra going to find? What was the old conductor's name? And the woman waiting for her son to come home — she doesn't yet know the one she's waiting for is already gone.

You don't know either. All you know is that you are here. In a compartment that shouldn't exist. In the very heart of the Void Sea.

And you are not yet dead.

**—— Chapter 1 Demo Complete ——**

The full version contains four chapters and three endings. Thank you for playing.

@end

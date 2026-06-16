@item white_pill
name: White Pill
desc: A white tablet with a faint grassy smell. The label is half-torn, leaving only a handwritten character: 'An...'
usable: true
effect: sanity_restore 1
consume: true
@enditem

@item pistol
name: Standard-Issue Pistol
desc: A dark, cold service pistol. Found under the sofa. Three rounds left in the magazine.
usable: false
bullets: 3
@enditem

# Opening
@bg: assets/bg_开场.png

## wake_up
You are waking up.

No — more precisely, you are in the process of waking. Consciousness seeps upward like water beneath thin ice, slow and uncertain. You feel yourself floating on some kind of boundary: darkness on one side, a grey-white light on the other.

The back of your head is pressed against cold metal.

→ first_look

---

## first_look
### Narrator
You open your eyes.

The ceiling is low. Rivets. Joints between metal plates. A yellow-amber light sways gently overhead with a rhythm — like something underwater.

A low, steady hum. Not tinnitus. It comes from inside the walls.

→ stand_up

---

## stand_up
### Narrator
You try to stand. Your legs are weak — not from exhaustion, but from a more fundamental strangeness, as if these muscles do not belong to you, as if you have not yet settled into whatever relationship you have with this body.

You brace yourself against the wall. It vibrates.

? Look around. → look_around
? "Anyone there?" → call_out

@end

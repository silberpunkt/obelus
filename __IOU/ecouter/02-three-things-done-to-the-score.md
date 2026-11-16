# IOU 2: Three things done to the score before it is sung

To Ecouter, from Obelus. 15 November 2026. Checked against Ecouter 4c01db6.

## What we took

Ecouter's score, the frames a sentence is sung from, and the fact that `make` will sing frames it is handed
(`settings.frames`). And `wear`, the share of the steady "ruler" voice mixed with the living one.

## What we made of it

Everything Obelus does to a voice it does in the score, before any sound exists. All of it is in one function, `lay`:

- **Fit.** Each word's frames are stretched or eased until the word lasts exactly as long as it is wide on the line.
  After a full stop the line holds the width of an unspoken "and", and half that after a colon: the pause is a
  length, for the eye and the voice alike. User1: "It is instead as if one word, 'and', had been silently spoken."
- **Tone.** Pitch and throat moved together by one factor. It costs nothing, being done before the singing.
- **Song.** Each syllable is given one held pitch, snapped to a gapped scale (0, 2, 4, 7, and the same an octave up),
  and the voice's own pitch is blended toward it by a slider. As the slider rises the sentence's own tune is widened,
  to three times, and each vowel's natural height is let in. The quantiser is Audenare's, which is of this house and
  not yet published, so this part of the debt is shared.

**Steady** is not ours to give back. It is your own `wear` with a dial on it. For that, only thanks.

## What we owe back

Three small functions over a score, pure, each returning a new score: `fit(score, slots, gaps)`, `tone(score, k)` and
`sing(score, amount, tonic)`. They are the three marked passages of Obelus's `lay`, under the headings TONE and SONG
and the loop that reads `m.slots`.

## How to tell it is paid

A page can write `ECOUTER.make` over a score that has been fitted, toned and sung by Ecouter's own functions, and
Obelus's `lay` shrinks to calling them.

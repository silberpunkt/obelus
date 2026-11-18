# IOU 1: The tape, and a head that does not pop

To Ecouter, from Obelus. 15 November 2026. Checked against Ecouter 4c01db6.

## What we took

`ECOUTER.make`, which gives a sentence back as finished sound. Ecouter itself plays nothing: it hands over the samples,
and its example `examples/say.html` plays them as one whole buffer.

## What we made of it

A text as a tape. Each sentence is sung whole, ahead of need; every word of it is fitted to the width of its word on
the line; and a head reads the tape at the place where the line stands, at the pace the line moves, forward or back.
So the voice can be dragged, thrown and scrubbed, and cannot drift from the text.

The head was first a ScriptProcessor. That is answered on the thread that paints the page, within one small buffer,
and a frame of Obelus often takes longer. What followed, on one evening and four engines:

| Engine | Head on the painting thread | Head on the audio thread |
|---|---|---|
| Chromium (Edge, Brave), by User1's ear | static pops, four to six a second | "play beautifully" |
| Chromium, headless, by count over 16 s | 130 clicks, 8 a second, the largest a jump of 1.22 of full scale | 0 clicks, largest jump 0.07 |
| Gecko (LibreWolf), by User1's ear | no pops: it waits for a late answer | no pops |
| Servo 0.8.0 | the only head it has | it has no AudioWorklet |

Run off line, the new head gives the old head's output exactly (correlation 1.00000). Both recordings are in
`samples/`.

Two courtesies were learned on the way. A machine with no sound device refuses `resume()` with a rejected promise
(WebKit says so aloud), and Servo refuses to make an audio context at all. Each wants a catch.

## What we owe back

- **A note for `docs/how-it-works.md`**, on playing what Ecouter makes: a whole buffer never pops; a stream must be fed
  from the audio thread; and the table above.
- **An example, `examples/tape.html`**: a sentence, a slider, and a head. It can be cut from Obelus's `HEAD_SRC` (the
  head), `headSync` (what the page tells it each frame) and `headUp` (which keeps the old head where there is no
  worklet).
- **Two guards in `examples/say.html`**, where the audio context is made (its line 100): a `try` about the making, and a
  `catch` on `resume()`.

## How to tell it is paid

Ecouter's examples hold a player whose voice can be dragged; its running sound, caught in Chromium, has no clicks; and
`say.html` opens without error in a box that has no sound.

## Paid in part

18 November 2026, by Ecouter's commit 031ea1e. The note is written: `docs/how-it-works.md` has a section, "Playing
what Ecouter makes", with the table above in it. The two guards are in `examples/say.html`, and in the other two
example pages as well; all three were opened and pressed in Chromium, Firefox and WebKit, and in a box made to refuse
a context, without error. Still owed: `examples/tape.html`, a voice that can be dragged.

## Paid

18 November 2026, by Ecouter's commit 9230fae.

Ecouter now has a player, its second ring: `ecouter-player.js`, beside the library as `ECOUTER.PLAYER`. It is this
page's head with the line taken out of it: the tape is measured in seconds where ours is measured along a line of
type. It runs on the audio thread, keeps the old head for an engine that has no worklet, and carries both guards. One
thing was added on the way home: the head never jumps in loudness. Starting, stopping and being lifted are each a ramp
of four thousandths of a second.

`examples/tape.html` is the example that was owed: a sentence, the eight voices, a pace that runs through nought to
backward, and a picture of the tape to take hold of.

How it was told to be paid. Its running sound was caught in Chromium while it was played whole, dragged forward, held
still, dragged backward, and turned round by the pace: no gaps and no clicks, the largest step between two samples
0.06 of full scale. In a box made to refuse a context the page carries on and says that nothing can be heard. In
Firefox and WebKit the head was run off line in each engine's own worklet, and spoke forward and backward. Then User1
tried it by hand and ear: "It played perfectly by itself. I grabbed it... it moved the playhead and sounded out
correctly as a record would, as a tape would." And: "I detected nothing wrong."

Not done, and not owed: Obelus still reads its line with its own head. It may come to ask Ecouter for one.

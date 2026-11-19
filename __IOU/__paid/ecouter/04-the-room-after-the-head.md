# IOU 4: The room belongs after the head

To Ecouter, from Obelus. 15 November 2026. Checked against Ecouter 4c01db6.

## What we took

`mellow`, which Ecouter already has and which the house finish uses: the highs shelved down above about 2 kHz, a small lift below about 250 Hz, and a little room (two early echoes and a short decaying one, 120 ms of tail). It is done to the finished sound. So the idea of giving the voice its presence is yours, and was there first.

## What we made of it

**Resound**: the same intent, placed after the head and done live. User1's rule for a speaking machine: "TTS voices are rarely given their presence: treble-, bass+, slight bright reverb as if listening to a friend in a wooden sunlit room. That's all they need."

- a lift at the chest of the voice: 170 Hz, 3 dB, Q 0.8
- a little taken from the top: above 4.2 kHz, 2 dB
- a return that begins 12 ms after the voice, is scattered and not regular, has lost a little brightness, is gone in a quarter of a second, and lies 11.8 dB under the voice

It took three tries. The first was "a metal elevator". The second put the voice "onto a floorway of the Death Star". The third is the one above.

Why after the head: a tape that is dragged or run backward drags whatever is on it. A room laid into the sound is played backward with the voice. A room after the head is the air about the machine, and stays still.

## What we owe back

The three numbers, the finding about where a room goes, and one open question we have not answered. With Finish and Resound both on, as Obelus opens, there are two rooms: `mellow`'s on the tape and Resound's after it. Nobody has yet listened for whether that is one too many.

## How to tell it is paid

Ecouter's notes say where a room belongs for a voice that is played and for one that is scrubbed, and the two-rooms question has been answered by ear.

## Paid in part

18 November 2026, by Ecouter's commit 031ea1e. Ecouter's notes now say where a room belongs: laid into the sound for a voice played whole, and after the head for one that is scrubbed. Still owed: Resound itself, which belongs with the player that Ecouter does not yet have; and the two-rooms question, which nobody has yet listened for.

18 November 2026, by Ecouter's commit 9230fae. Resound is paid: it is in Ecouter's player ring, with the three numbers as they stand above, after the head, and held in Ecouter's test against the room as Obelus makes it, to the last bit. One thing was found on the way: the lift and the return together raise the peak of the voice by as much as a third, which at full volume is clipped at the loudspeaker; so Ecouter's player opens at this page's volume, 0.8. Still owed: the two-rooms question. `examples/tape.html` now has the two rooms as two buttons, Mellow and Resound, so that an ear can try each alone and both together, backward as well as forward.

## Paid

18 November 2026. The last part was the two-rooms question, and it is answered by ear.

User1 tried the two rooms in Ecouter's `examples/tape.html`, where Mellow (the room on the tape) and Resound (the room after the head) are two buttons. His answer: "I confess that while Mellow is vivid and immediate, the effect of Resound is nearly undetectable subjectively at the moment. Yet it sounds no worse and ... that settles it. Lauren achieves her depth with both. Please keep both."

So two rooms are not one too many. Both stay, in Obelus as it opens and in Ecouter's player.

One correction to what is written above. The rise in the peak was first measured over four voices, and found to be a third. Over all eight it is nearer a half (Nuage, Phillippe and Arthur the most), so Ecouter's player now opens at 0.72 and not at this page's 0.8 (its commit 9f90631). On this page, at 0.8, Obelus himself stands clear; Arthur, Nuage and Phillippe may touch full scale now and then. That is noted here and not yet mended.

The rest was settled before: Ecouter's notes say where a room belongs (its commit 031ea1e), and Resound itself is in its player ring (9230fae).

# birth_music
##### A program to create an original song based on a birthday inputted

by Jane Plomp

---

## How Does the Program Decide What to Play?

#### Or rather, how do I think a birthday should be translated into song?


The actual **birthday numbers get converted into a sequence of non-key specific chords, starting with 1 = I**. So my birthdday, `07211997` turns into `vii°, vii°, ii, I, I, ii, ii, vii°` (in the actual code I just use solfege, so that gets listed as `ti(low), ti, re, do, do, re(high), re(high), ti`.

However, that makes a pretty short song! Thus I expanded it in this way: **The birthday pattern repeats, but a number is added to the number pattern so a new chord pattern is created.** The amount moved up depends on the year born, and there are six possible changes (this partially relates to the Chinese zodiac, although each animal shares the same change with one other animal). I was born in the year of the ox (1997) so my pattern gets moved up by 6... `07211997` --> `63877553`, **Then I repeat the original tune, and end on a I chord** (because ending on I sounds more complete). Thus my total note pattern would be: `07211997 6377553 07211997 1`. **This makes an ABA musical pattern that seems cohesive while adding something new.**

Then, **based on the month you were born, those non-key specific chords get converted to a particular key.** There are 12 major keys in Western music, so I use those, with January starting on Ab and each month bringing the key up by a half step. For me, being born in the 7th month, my song is in the key is D major.

The **tempo of the song is based on the day you're born (1 to 31).** A higher birthday is a slower song (The actual equation: `1 + day*0.025 seconds` = The length of a chord). For me, being born on the 21st, my birthday is on the slower side, so each chord lasts 1.525 seconds.

There's also **alternation between playing normal chords and apreggio-like patterns for each chord. This pattern is based on the day you were born (even, odd, or prime).** It is an eight-note pattern that is repeated three times through the whole song. If 1=Arpeggio, 0=Plain chord, then if you were born on an even day: `[1,1,0,0,1,1,0,0,]`. If you were born on a non-prime odd day: `[1,1,1,1,0,0,0,0]`. If you were born on a prime day: `[1,0,1,0,1,0,0,0]`. Since I was born on the 21st, I have the arpeggio pattern for the non-prime odd day.

The actual arpeggio pattern is composed of three isolated notes from the chord, plus the actual chord itself, playing separately on four beats in a chord section (so like four quarter notes in a measure). Which beat exactly has the chord play is affected by season and year born.

The first four notes in each eight note section is affected by year born (even/odd). Even numbered years have the chord played on the 1st beat, odd numbered years have the chord played on the 3rd beat. Since I was born in 1997, and odd year, my chord would be played on the 3rd beat for the first four notes of each eight note pattern, assuming they are apreggio notes (which they are according to my arpeggio pattern: `[1,1,1,1,0,0,0,0]`).

The last four notes in each eight note section is affected by season born. Spring has the chord played on the 1st beat, summer on the 2nd, fall on the 3rd, and winter on the 4th. Since I was born in summer, theoretically arpeggios in the last four notes of each eight note pattern would have the chord on the 2nd beat. However, my arpeggio pattern has only chords for those notes, no arpeggios, so it does not affect my song (my arpeggio pattern is `[1,1,1,1,0,0,0,0]`).

If something is a normal, non-arpeggiated chord, but the next chord is either a third or a sixth above/below, then **passing notes** are added in in the second half of the measure.

Thanks for checking out my program! If you have any questions, feel free to message me.

P.S.: I used [tone.js](https://tonejs.github.io/) to produce the tones used in this project.

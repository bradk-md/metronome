# Metronome
I've updated index.html with chord diagrams and microphone chord detection. I checked it two ways: the page loads with no errors and all 14 diagrams render correctly. Before adding detection, I ran its algorithm on simulated guitar strums of all 14 chords and it named every one correctly, including major vs. minor. I haven't tried it on a real guitar.

Chord diagrams

A diagram appears next to the chord name for every chord in your list.
It shows open strings (○), muted strings (✕), finger numbers, barres, and a fret marker like "3fr" for Cm and Gm.
The diagram changes on beat 4 along with the chord name, so you see the next shape before you have to play it.

Chord detection

Click 🎤 Enable Chord Detection. It shows "You played: X" in green with ✓ when it matches the chord you should be playing, and in red with "✗ Expected C" when it doesn't.
Each measure counts against the chord announced for it, so the beat-4 preview doesn't mark you wrong while you're still holding the current chord.
It keeps a running score (e.g. "7 / 9 measures"), which resets each time you press Start.
With the metronome stopped, it works as a free-play chord identifier.
A level meter shows how loud the mic is hearing you. The orange line is the trigger point, which you can move with the new Mic Sensitivity slider in Settings.

Things to know

Opening the file: browsers only allow mic access on https:// or http://localhost pages. Double-clicking the file works in Chrome but may be blocked elsewhere. If you get a mic error, serve the folder locally (for example, python -m http.server) or host it the way you host your other tools.
Speakers vs. headphones: through speakers, the mic would hear the clicks and voice announcements, so the app ignores audio just after each click and while the voice is speaking. At fast tempos that leaves little listening time.
With headphones, turn on Using Headphones in Settings and it will listen continuously.
The Texas Blues kit has a long ride cymbal, so it gets the largest gap.
What it detects: it identifies major and minor triads in any key. A wrong note or a muffled string that changes the chord (for example, missing the minor third) will show as a different chord or not register. A slightly buzzy note usually still passes, so treat a ✓ as "right chord" rather than "perfectly clean."

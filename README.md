# csaea-project-week-1

### My project: MIDI File Scale Analyzer

These past couple of days, I have been working on a scale analyzer. It uses the public source code repo [JMidi's](https://github.com/Nit123/JMidi) MIDI file analyzer code and expands upon it, identifying a scale in a MIDI file and telling the user what it is. If I'm being honest, a lot of the original code is very hard for me to understand, since it's very complex, but I can explain what I added to it.

## How It Works ##

The basics of how it works are that it takes the notes analyzed by the original JMidi code and makes the first note the **root** note. That is the note that the scale will be named after. It then takes the next notes in the scale and matches them with one of the patterns in the scalePatterns 2D array. That pattern is assigned a scale type in the scaleTypes array. All that data is then returned to the user

**For example:** if a MIDI file starts with the note C, and then the subsequent notes are D, E, F, G, A, and B(optionally another C after to complete the octave), that is a C Major scale, so the JMidi code analyzes the notes, gives them to the scale analyzer, and then those notes are assigned a scale type(Major) and given a note name, which is the first note in the file, C.

This analyzer is relatively basic and only analyzes the following scale types:
* Major
* Natural Minor
* Melodic Minor
* Harmonic Minor
* Major Pentatonic
* Minor Pentatonic
It can also only really function if the MIDI file contains **only** the scale and nothing else. I do kind of want to make it so that it can look for scales and name them within a full-length song, but that would be too difficult for this short of a project(it could possibly be another project week tho!!).

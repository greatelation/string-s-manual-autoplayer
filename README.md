# string-s-manual-autoplayer

This program is a manual QWERTY autoplayer built with Python, Tkinter, keyboard hooks, and PyAutoGUI to simulate precise keypresses. It reads virtual piano sheets, converts them into playable notes, and lets the user perform them manually using a small set of play keys. Users control the tempo by tapping for short notes and holding for long ones. Notes and chords, including shifted symbols and both QWERTY and MIDI layouts, are translated into keyboard events. It also supports fast playing for rapid note sequences.

The interface is a compact always-on-top window with playback controls, a note preview, and a scrolled text area for sheets. Pressing play enters listening mode: each key press advances through the sheet, triggers the corresponding note or chord, and logs timestamps to display live notes-per-second (NPS). Stop ends the session and resets the UI for editing.

Sheets are parsed to recognize single notes and bracketed chords, stored as character lists with special symbols removed. The current note is highlighted during playback.

Keyboard hooks monitor three play keys. Each triggers a press-and-hold cycle for the note or chord, filtered by mode (QWERTY or MIDI). Shifted characters are handled automatically. Chords simulate real typing with per-key press and release events.

A delay system humanizes playback by adding tiny randomized timing between chord notes and releases. A toggle button indicates its state. Timestamps track each note to continuously calculate and display NPS in real time.
ㅤ


# **Features**
### Playback Control
- Play keys advance through the sheet and trigger the current note or chord
- Timing comes from your taps and holds rather than fixed BPM
- Accurate simulation of shifted keys, punctuation, and multi-key chords

### Sheet Handling
- Supports single notes and bracketed chords
- Supports fast playing for rapid note sequences
- Strips formatting characters and maps each symbol to a playable key
QWERTY and MIDI-style layout modes (WIP)

### Humanization
- Delay mode adds slight timing variation for more natural chord playback
- UI indicator shows when delay mode is active

### Interface
- Always-on-top window
- Live NPS(Notes-Per-Second) display
- Preview pane highlights the current note
- Scrollable text field for sheet input
- Play/Stop controls, layout toggle, delay toggle, and help popup

### Cleanup
- Keyboard hooks are restored when playback stops
- Shift and other simulated keys are released on exit
- Window cleanup routines prevent stuck keys


License
> This project is licensed under the [GNU General Public License v3.0](https://www.gnu.org/licenses/gpl-3.0.en.html)

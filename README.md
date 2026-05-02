# Finn's Number Music Machine

Type a sequence of numbers. Each number becomes a note. Press play. Hear math.

Built by Finn (age 9) and Dad, with Claude on the keyboard.

## How to run it

It's a single `index.html` file. No build step.

**On a laptop**: double-click `index.html`, or run a local server:
```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

**On Finn's iPad**: open the GitHub Pages URL in Safari → Share → "Add to Home Screen". It'll launch like an app.

## What it does (Weekend 1)

- Type any number sequence — or hit a preset button (π, Fibonacci, primes, phone number)
- Pick a scale (pentatonic always sounds happy)
- Adjust tempo and octave range
- Press ▶ Play

## How the numbers become notes

Each number `n` is mapped to a note like this:

1. Pick a **scale** — a list of allowed note offsets, e.g. C major pentatonic = `[0, 2, 4, 7, 9]`.
2. **Wrap** the number inside the scale: `degree = n % scaleSize`.
3. **Climb octaves** as numbers get bigger: `octave = floor(n / scaleSize)`.
4. Add it all to middle C and play it.

That's it. The whole musical brain is about 10 lines of code in `index.html`.

## Roadmap

See [`../context/project-pitch.md`](../context/project-pitch.md) for the 11-week plan. Short version:

| Week | Feature |
|---|---|
| 1 ✅ | Digit-to-note player, preset sequences, scales, tempo |
| 2 | More scales, custom scale builder |
| 3 | Two voices at once (harmony) |
| 4 | Rhythm from a second sequence |
| 5 | Piano-roll visualizer |
| 6 | Custom rule builder |
| 7 | Save & share via URL |
| 8 | "Describe a mood" → Claude picks parameters |
| 9 | Drum track |
| 10 | Record & export audio |
| 11+ | Finn's call |

## Files
- `index.html` — the whole app
- `journal.md` — session notes

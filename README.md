# schatten-lessons

Lesson content for **Schatten** (personal German shadowing app).

## How it works
- `manifest.json` — the lesson index. The app fetches this on refresh.
- `lessons/<id>/lesson.json` — one lesson: clips, chunks, German transcript,
  Persian translation, and **per-word start/end timings** (seconds, relative to the clip audio).
- `lessons/<id>/audio/*.mp3` — clip audio, cut at word boundaries.

## Adding a new episode
Musy (the agent) runs the pipeline per episode:
1. Download episode audio + German captions
2. Word-level forced alignment (Vosk `vosk-model-small-de-0.15`)
3. Cut 5–10s chunks at word boundaries
4. Persian translations
5. Bump `manifest.json` (`updated` + lesson entry)

Personal use only.

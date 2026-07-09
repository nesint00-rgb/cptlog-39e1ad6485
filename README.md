# The First Officer's Log

A private podcast feed for the Captain — briefings from the first officer: "what happened since"
update logs and dispatches. Subscribed to as a custom RSS feed in Podcast Addict.

- **Feed:** `feed.xml` (served by GitHub Pages)
- **Episodes:** `episodes/*.mp3` (+ optional `*.json` sidecar: title, description, pubDate, guid)
- **Art:** `cover.jpg`

## Locked template (2026-07-09)

- **Persona:** calm, warm, quietly competent starship *first officer* briefing the Captain
  (evocative — "systems nominal", "console" — but no direct franchise references).
- **Voice:** Gemini 2.5 TTS, voice **Kore** (primary). Backup: **Sulafat**.
  Generate with `gemini_tts.py` (model `gemini-2.5-flash-preview-tts`, officer style prompt).
- **Music:** original synthesized bed — `intro-sting.mp3` + `outro-pad.mp3` (built by `music_bed.py`).
  Cold-open pattern: intro sting -> voice over a soft bed -> outro pad.

## Add a new episode

1. Write the script; render narration:
   `python C:\Users\nesin\Scripts\radiolab-journal\gemini_tts.py <script.txt> Kore <name>.mp3`
2. (Optional) lay the music bed via `music_bed.py`.
3. Drop `episodes/<name>.mp3` (+ optional `<name>.json` sidecar) here, then:
   `python C:\Users\nesin\Scripts\radiolab-journal\build_feed.py --repo . --base-url https://nesint00-rgb.github.io/cptlog-39e1ad6485`
4. `git add . && git commit -m "add episode" && git push`

Podcast Addict refreshes the feed on its schedule and downloads the new episode.

Tooling lives in `C:\Users\nesin\Scripts\radiolab-journal\` (`build_feed.py`, `gemini_tts.py`,
`tts.py`, `music_bed.py`).

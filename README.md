# The First Mate's Log

A private podcast feed for the Captain — custom audio briefings and "what happened since"
update episodes. Subscribed to as a custom RSS feed in Podcast Addict.

- **Feed:** `feed.xml` (served by GitHub Pages)
- **Episodes:** `episodes/*.mp3` (+ optional `*.json` sidecar: title, description, pubDate, guid)
- **Art:** `cover.jpg`

## Add a new episode

1. Drop `episodes/<name>.mp3` (and an optional `<name>.json` sidecar for title/description/date).
2. Regenerate the feed:
   ```
   python C:\Users\nesin\Scripts\radiolab-journal\build_feed.py --repo . --base-url https://<user>.github.io/<repo>
   ```
3. `git add . && git commit -m "add episode" && git push`

Podcast Addict refreshes the feed on its normal schedule and downloads the new episode.

Generator + audio tooling live in `C:\Users\nesin\Scripts\radiolab-journal\` (`build_feed.py`, `tts.py`).

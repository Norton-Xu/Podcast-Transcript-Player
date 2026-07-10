# Philosophize This! Transcript Player

Static first version for listening to Philosophize This! with transcript reading.

## What it does

- Opens directly to the episode list.
- Dark mobile-first reading UI: the main screen is the player plus transcript.
- Episode selection lives in a collapsed left-side drawer.
- The drawer closes by tapping the backdrop, pressing Escape, selecting an episode, or swiping left.
- Main controls use a compact icon toolbar; search opens only when requested, and follow is a simple on/off icon toggle.
- Uses the fixed RSS feed: `https://feeds.megaphone.fm/QCD6036500916`.
- Reads the transcript directory: `https://www.philosophizethis.org/transcripts`.
- Matches audio and transcript by episode number.
- Defaults to the newest episode that already has a transcript.
- Keeps newer audio-only episodes visible in the list.
- Sorts episodes from oldest to newest in the drawer.
- Falls back to public CORS/readability endpoints if direct browser fetching is blocked.
- Loads audio in the browser player.
- Extracts transcript paragraphs from the episode transcript page.
- Highlights the current paragraph based on playback progress and paragraph text length.
- Saves current episode, playback time, settings, and loaded transcripts in browser storage.

## Options

The visible options are intentionally small:

- Intro offset, sec
- Outro offset, sec
- Paste transcript manually, used if the browser blocks automatic transcript loading
- Follow audio toggle near the transcript search box

## Limits

- This is still a static HTML page. It uses public fallback endpoints as a prototype convenience, which is less reliable than your own small proxy API.
- Highlighting is approximate. It maps audio progress to transcript paragraph position, improved by text length; it is not timestamp-level sync.
- iOS browsers require a manual tap to start audio playback.

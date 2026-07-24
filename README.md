# Philosophize This! Transcript Player

Static mobile player for listening to Philosophize This! with transcript reading.

## What it does

- Dark, mobile-first reading UI: the main screen is the transcript and a fixed bottom player.
- Episode selection lives in a collapsed left-side drawer.
- The drawer closes by tapping the backdrop, pressing Escape, selecting an episode, or swiping left.
- Main controls use a touch-friendly player with 15-second circular seek controls, a centered play button, and a large progress slider.
- Search stays visible below the title; every matching word or phrase is highlighted inline in the transcript.
- Follow audio is a simple on/off icon toggle beside search.
- Use the pin icon beside Follow to calibrate the transcript: tap it, then tap the word currently being spoken. Multiple saved anchors keep the approximate follow position aligned across an episode.
- Uses the fixed RSS feed: `https://feeds.megaphone.fm/QCD6036500916`.
- Reads the transcript directory: `https://www.philosophizethis.org/transcripts`.
- Matches audio and transcript by episode number.
- Sorts episodes from oldest to newest and selects episode 001 on a true first visit.
- Keeps newer audio-only episodes visible in the list.
- Falls back to public CORS/readability endpoints if direct browser fetching is blocked.
- Loads audio through the browser audio element behind a custom mobile-friendly player.
- Integrates with supported system media controls for episode metadata, progress, and 15-second seek actions.
- Extracts transcript paragraphs from the episode transcript page.
- Highlights the current paragraph based on playback progress and paragraph text length.
- Saves the current episode, playback time, settings, loaded transcripts, RSS feed, and transcript index in browser storage.
- Shows a light `Resume 12:34` or `Finished` marker for episodes you have listened to.
- Restores a cached transcript and episode menu immediately on later visits while refreshing remote data in the background.
- Fetches RSS and the transcript directory in parallel, so a first visit can begin loading episode 001 as soon as RSS arrives.
- Is installable as a small PWA on GitHub Pages. The app shell works offline after the first visit; cached transcripts and listening progress remain available in the same browser.
- Uses original [Phosphor Icons](https://phosphoricons.com/) SVG assets; see `THIRD_PARTY_NOTICES.md` for the MIT license.

## Options

The visible options are intentionally small:

- Intro offset, sec
- Outro offset, sec
- Paste transcript manually, used if the browser blocks automatic transcript loading
- Follow audio toggle near the transcript search box
- Reset the current episode's manual transcript calibration

## Limits

- This is still a static HTML page. It uses public fallback endpoints as a prototype convenience, which is less reliable than your own small proxy API.
- Highlighting is approximate. Manual anchors improve alignment, but it is not timestamp-level or word-level sync.
- iOS browsers require a manual tap to start audio playback.
- Cached content is local to the current browser and device. It does not sync between devices.
- Audio files and newly opened transcripts still need a network connection; the PWA cache deliberately avoids downloading large podcast audio automatically.

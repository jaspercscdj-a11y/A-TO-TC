# OPPA SUBS — iPhone Web App prototype

This is a progressive-web-app (PWA) front-end prototype. It is not yet a production subtitle translator.

## Included now
- iPhone-friendly responsive interface
- Home-screen PWA manifest and service worker
- YouTube URL format check
- Local SRT/VTT import and timestamped Korean subtitle preview

## Not implemented yet
- Fetching captions from arbitrary YouTube videos
- Extracting or downloading YouTube audio/video
- Korean speech recognition (ASR)
- AI Traditional Chinese translation
- Synchronized subtitle playback over a YouTube player

## Important YouTube/API limitation
The official YouTube Data API requires OAuth for caption listing, and downloading a caption track requires permission to edit the video. Therefore it cannot be assumed that a third-party app can fetch captions for any public YouTube video. See:
- https://developers.google.com/youtube/data/reference/rest/v3/captions/list
- https://developers.google.com/youtube/data/reference/rest/v3/captions/download

## Next production architecture
1. Caption source adapter: use creator-authorized captions or a user-provided subtitle file.
2. If no authorized caption source is available, accept user-provided audio/video files that the user has rights to process.
3. Korean ASR service returns Korean text with timestamps.
4. Translation service converts each segment to natural Traditional Chinese while preserving casual speech, jokes, and forms of address.
5. Web player renders translated subtitles and allows SRT/VTT export.

Do not put API keys in browser JavaScript. A secure backend is required for any paid AI API.

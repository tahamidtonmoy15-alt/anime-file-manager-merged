# Anime Watching Tracker

An English-only Android anime library and watching tracker with a premium dark purple/cyan glass interface.

## Visual design

- Premium light Lavender + Ice Blue Glassmorphism theme with soft gradients, translucent cards, refined shadows, rounded controls and improved typography.
- Responsive mobile header with a swipeable action strip; the content no longer scrolls visibly beneath a transparent multi-row toolbar.
- Matching visual styling across the anime catalogue, statistics, filters, category tabs, Watching Tracker, episode rows, Weekly Schedule, File Manager, add/edit dialogs and video player.
- This is a presentation-only redesign. Existing JavaScript, storage keys, catalogue, poster data, controls, playback and file-management logic are retained.

## Included

- Bundled 251-title catalogue from the supplied list, grouped into Action/Adventure, Fantasy/Isekai, Romance/Drama, Mystery/Thriller, Sports, Comedy/Slice of Life, Sci-Fi/Mecha, Horror/Supernatural, Anime Movies, Classic TV Anime, OVA/Specials, Donghua and Latest Hindi Dub Releases. Supplied dub labels are carried as Confirmed, Partial, Needs verification, Classic TV Dub, Hindi Audio Listed, Latest Hindi Dub and To Be Verified.
- Anime poster lookup, custom poster upload, add/edit/delete, search, category and watch-status filters, and A–Z / Z–A sort.
- Weekly Schedule button with All Days and Monday–Sunday filters. Anime with a saved Weekly Release Day appears automatically; Open Episodes opens its File Manager folder.
- Watching Tracker with year, weekly release day, seasons, manually addable episode numbers per season, individual watched ticks and progress. Clicking an anime poster opens its Weekly Release Day picker; the picker can also create/open its episode tracker.
- Local episode File Manager grouped by anime and season; videos are copied into app storage, sized, played, renamed, deleted and downloadable individually.
- Each tracked episode can store its own video file, then play internally or open it in another compatible Android player. Replacing or deleting a linked video updates the tracker association. Weekly release day remains selectable separately from the anime card and Episode Tracker.
- Built-in WebView player with seek, skip, speed, volume, brightness, subtitle loading and best-effort audio-track selection.
- Android Open in Other Player action using the system compatible-app chooser.
- JSON backup/restore for custom anime, statuses, Watching progress and poster references.
- GitHub Actions debug APK build with Node 20 and Java 17.

## Build

1. Open the repository's Actions tab.
2. Select **Build Anime Watching Tracker APK**.
3. Select **Run workflow** (pushes that change this project also start a build).
4. Open the completed run and download the **anime-watching-tracker-apk** artifact.
5. Extract the artifact ZIP and install **Anime-Watching-Tracker.apk**.

## Important notes

- Videos are stored as Blobs in app IndexedDB. Deleting the original Gallery file does not remove the app's copy. Deleting a video in File Manager frees that stored copy; Android uninstall/clear-data removes app storage.
- JSON backups do not include large video blobs. Use File Manager's Download action to export a video, and Upload Episodes to add it back.
- Bundled catalogue and saved tracker details work offline. Remote poster lookup needs internet for titles whose poster has not yet loaded/cached; a local placeholder is used when lookup fails.
- Internal video playback depends on Android WebView codecs. MKV, HEVC, 10-bit and unusual audio codecs are not guaranteed. External-player handoff opens Android's compatible-app chooser; installed player and codec support determine playback.
- Audio-track selection is best-effort because many WebView versions do not expose the audioTracks API. Subtitle rendering depends on WebView support for the selected SRT/VTT subtitle.
- This version uses the WebView player and Android external-player bridge; it does not yet bundle a native LibVLC engine. Playback must be tested on Redmi 13C / Android 15 before being marked verified.
- Hindi-dub labels and release dates come from the supplied list and have not been independently re-verified by this build.


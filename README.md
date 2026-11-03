# Anime File Manager — Android APK

This project builds a debug Android APK with GitHub Actions. The app includes an anime catalogue, category filters, watch lists, poster loading/custom posters, season-aware episode folders, local episode storage, an in-app HTML5 video player, and an Android external-player handoff. Anime Reels are not included.

## Build the APK

1. Upload the contents of this ZIP to the root of a GitHub repository. Keep the `.github` folder.
2. Open **Actions** in the repository.
3. Select **Anime File Manager - Build APK**.
4. Choose **Run workflow** and confirm.
5. When the run succeeds, open it and download the `anime-file-manager-apk` artifact.
6. Extract the artifact ZIP and install `Anime-File-Manager.apk` on Android.

Pushing a commit to `main` or `master` also starts a build.

## Notes

- This is a debug APK. Android may ask permission before installation.
- App ID: `com.hda.anime`; display name: `Anime File Manager`.
- Uploaded episode videos are stored in the app WebView's IndexedDB storage. Device storage limits and WebView quota policies apply. Deleting an episode inside the app frees its stored data; uninstalling the app removes its app data.
- The built-in player uses the Android WebView media engine. The External Player option hands the video to an installed compatible player. No app can guarantee playback of every damaged file or every codec without testing on the target phone.
- Posters from public sources require an internet connection; custom posters can be selected when adding an anime.
- Anime Reels are intentionally excluded.

<p align="center">
  <img src="assets/app-icon.png" width="128" height="128" alt="Shelf app icon">
</p>
<h1 align="center">Shelf</h1>
<p align="center">An Android player for audiobooks, videos, and long-form media.<br>
Syncs with Google Drive — stream, download, and pick up where you left off.</p>
<p align="center"><strong>Version 1.0.0</strong> · Android 8.0+ (API 26)</p>

<p align="center">Also available for <a href="https://github.com/madebysan/shelf-ios"><strong>iOS</strong></a> and <a href="https://github.com/madebysan/shelf-mac"><strong>macOS</strong></a></p>

## Features

- **Google Drive streaming** — Play audio and video files directly from your Drive, no downloads required
- **Offline downloads** — Save books locally for listening without internet
- **Background playback** — Keep listening with the screen off via MediaSession
- **Mini player** — Persistent playback controls on the library screen
- **Cover art** — Automatic cover art fetching from iTunes, Google Books, and Open Library
- **Multiple libraries** — Add, switch, and manage separate Drive folder libraries
- **Search, filter, and sort** — Find books by title, author, or genre with filter chips and sort options
- **Genre browsing** — Visual genre cards with cover art collages
- **Discover mode** — Shuffle to a random book at a random position, progress not saved
- **Bookmarks** — Save and jump to named positions within a book
- **Chapters** — Navigate chapter markers when available
- **Sleep timer** — Timed or end-of-chapter auto-pause
- **Playback speed** — Adjustable speed control
- **Video playback** — Dedicated 16:9 player with 10-second skip for video files
- **Star, hide, and complete** — Organize your library with status flags
- **Ratings** — Rate books on a 5-star scale
- **Progress export/import** — JSON backup compatible with the iOS version
- **Dark mode** — System, light, or dark theme
- **Haptic feedback** — Tactile responses on long-press actions

## Tech Stack

- **Language:** Kotlin
- **UI:** Jetpack Compose + Material Design 3
- **Architecture:** MVVM with Clean Architecture layers (data/domain/UI)
- **DI:** Hilt
- **Database:** Room (SQLite) with 3 tables (books, libraries, bookmarks)
- **Networking:** Retrofit + OkHttp for Google Drive API
- **Playback:** Media3 (ExoPlayer) + MediaSessionService
- **Preferences:** DataStore
- **Image loading:** Coil

## Project Structure

```
app/src/main/java/com/madebysan/shelf/
├── data/
│   ├── local/          # Room database, DAOs, entities
│   ├── preferences/    # DataStore user preferences
│   ├── remote/         # Drive API service and DTOs
│   └── repository/     # Data repositories
├── di/                 # Hilt dependency injection modules
├── domain/
│   └── usecase/        # Business logic (scan library, fetch covers)
├── service/
│   ├── auth/           # Google Sign-In and OAuth
│   ├── download/       # Offline download manager
│   ├── drive/          # Drive file operations
│   └── playback/       # ExoPlayer service and state management
└── ui/
    ├── component/      # Reusable composables
    ├── navigation/     # Navigation graph
    ├── screen/         # Screen-level composables and ViewModels
    └── theme/          # Material theme and colors
```

## Building

1. Open in Android Studio
2. Add your `google-services.json` to `app/`
3. Configure Google Drive API credentials in Google Cloud Console
4. Build and run on a device or emulator

## Related Projects

| Platform | Repository |
|----------|-----------|
| iOS | [shelf-ios](../shelf-ios) |
| macOS | [shelf-mac](../shelf-mac) |
| Landing | [shelf-landing](../shelf-landing) |

## License

[MIT](LICENSE)

---

Made by [santiagoalonso.com](https://santiagoalonso.com)

# Release notes

## 0.13.1 — July 14, 2026
### 🐛 Fixed
- The app could crash right after signing in on a freshly reset library, before the TMDB API key had time to sync back down
### 🔧 Improved
- Native Android back gesture (edge swipe) support
- Internal app naming cleanup for consistency

## 0.13.0 — July 14, 2026
### ✨ New
- In-app announcements: an important message can show as a banner or a popup on launch, published directly on GitHub without a new app version
- New **Help** screen (Profile): the user guide is now readable in-app, formatted into color-coded sections instead of plain text
- Remove a show or movie from the library directly from its detail screen (trash button, with confirmation)
### 🐛 Fixed
- The add button on Search results now navigates straight to the added title's detail screen; going back returns to the Series/Films home instead of the Search screen
- Resetting the library then uninstalling/reinstalling the app could bring old shows back and auto-sign you in — Android's default auto-backup, which was restoring a stale local copy, is now disabled
### 🔧 Improved
- The back arrow has a more polished look across every screen that uses it
- In-app updates now follow real version numbers instead of triggering on every new commit
- Stronger protection on Auth/Firestore access (Firebase App Check)

## 0.12.0 — July 13, 2026
### ✨ New
- Library is split back into two dedicated tabs, Séries and Films, each with its own filter, search, and grid/list toggle — searching from Séries only searches shows, and from Films only movies
- The Search screen is fully redesigned to match the rest of the app (poster cards, sections), with a clear button and a genre filter
- Home now has a search button (covering both series and movies) and an "Upcoming" section, matching Séries/Films
### 🔧 Improved
- Search no longer fires a network call on every keystroke: longer debounce and a 2-character minimum before it queries

## 0.11.0 — July 13, 2026
### ✨ New
- Person pages now show an Awards & Nominations section (via Wikidata, since TMDB has no awards data)
- Show/movie pages now have a clickable Crew section (director, writer, composer, creator) alongside Cast — tap through to their person page just like an actor
- Home's greeting now reflects the time of day and your first name when signed in, instead of a flat "Bonjour"
### 🐛 Fixed
- The in-app update could fail to install with a generic "problem with the app file" error and no way to understand why — a failed download is now caught and shown as a real, retryable error
- Home's discovery rows (and the person page's filmography) shifted around while scrolling because card height varied by title length — every card now reserves a consistent height
- The Continue Watching progress ring and episode text could become unreadable on a bright/light backdrop image — both now sit on a dark scrim so they stay legible regardless of the artwork
### 🔧 Improved
- Cast/Crew rows widened so full names are actually readable instead of truncated to a few letters
- Crew job titles (Director, Writer, Composer, Creator) are now translated instead of always showing the raw English TMDB term

## 0.10.0 — July 13, 2026
### ✨ New
- Home is now a discovery hub instead of repeating the Library grid: Suggestions based on your library, Trending Now, and Latest Movie/Show Releases, alongside Continue Watching — all via TMDB, no paid third-party service
- Person pages now show a full filmography (TMDB combined credits), with posters linking to each title
### 🐛 Fixed
- Dates (birthday/death date, upcoming release dates) were shown as raw ISO strings instead of following the app's language — a French device would still see "1955-01-18" instead of "18 janvier 1955"
- A long character name on a filmography poster could push the release year off-screen
### 🔧 Improved
- Person pages redesigned into cards (biography, filmography), matching the show/movie detail screens
- An actor/actress biography now falls back to English when TMDB has no translation for the app's language, instead of showing an empty biography

## 0.9.0 — July 13, 2026
### ✨ New
- Tapping an episode opens a detail sheet with its image, title, air date, rating, and overview
- Checking an episode now auto-fills every earlier unwatched episode in the season (catch-up); long-press a checkmark to toggle just that one episode individually
### 🐛 Fixed
- The season "mark all watched" checkmark only ever marked watched — tapping it while the season was fully watched now un-marks the whole season
- The episode detail sheet's mark-watched button could get stuck reflecting a stale state and stop responding to repeated taps
- The episode detail sheet could cut off the mark-watched button on long overviews — its content now scrolls
### 🔧 Improved
- Episode list rows redesigned as cards with a clearer watched state
- Show/movie detail "About" sections split into cards (overview, schedule, cast, watch providers), matching the Stats screen's look

## 0.8.0 — July 13, 2026
### ✨ New
- Charts (weekly/monthly/weekday) are now tappable to reveal a bar's exact value
- The "Shows by status" breakdown now opens a detail view, same as genres and networks
### 🐛 Fixed
- The theme followed the phone's system light/dark setting instead of always using the dark "Aubergine" theme — on a phone in light mode, the app rendered in very different, unfinished-looking colors
- Genre/network detail panels were capped in height and didn't show the full list — they now open full-screen, fully scrollable
### 🔧 Improved
- Favorite genres ranking now shows 10 genres instead of 5
- Detail lists (genre/network/status) are now sorted alphabetically

## 0.7.0 — July 13, 2026
### ✨ New
- "Reset library" button in Profile > Account
- App version and release notes are now viewable in Settings
### 🐛 Fixed
- The TV Time import screen got stuck at 100% (cloud sync was blocking the summary screen)
- Resetting the library was very slow (documents were deleted one at a time)
### 🔧 Improved
- Profile buttons now line up in a uniform grid
- More readable stat numbers (thousands separators, no more overflow)
- Total watch time now shown as months/days/hours
- TV Time import screen: shorter text, direct link to gdpr.tvtime.com, collapsible details

## 0.6.0 — July 13, 2026
### ✨ New
- Import your library from TV Time: shows, movies, and watch history, automatically matched on TMDB
### 🔧 Improved
- Clearer explanation of which file to pick on the TV Time import screen

## 0.5.0 — July 13, 2026
### 🐛 Fixed
- A show/movie's status didn't switch to "Completed" once fully watched
- The "Completed" stat and library-completion percentage stayed stuck at 0
- The "Shows airing" stat stayed stuck at 0
### 🔧 Improved
- Network breakdown stats can now be drilled into, same as genres
- More breathing room across charts and sections

## 0.4.0 — July 12, 2026
### ✨ New
- In-app update checking and installation
- Account deletion
### 🔧 Improved
- Redesigned login screen (logo, gradient, Google sign-in)
- Sync extended to followed shows/movies, watched episodes, and the watch log
- Stats and Settings merged into a single Profile tab
- Richer stats charts (estimated time remaining, weekly average, breakdown by status/network/day)

## 0.3.0 — July 12, 2026
### ✨ New
- New "Aubergine" theme (colors, typography, shapes)
- 4-tab navigation: Home, Library, Stats, Settings
- Home screen with a "Continue watching" carousel
- Favorites for shows and movies
- Sign-in and cross-device sync via an account

## 0.2.0 — July 12, 2026
### ✨ New
- Trailers, clickable cast, and a dedicated page for each actor/director
- Networks and broadcast status on the show page
### 🔧 Improved
- All episodes now load as soon as a show is added (reliable progress from the start)
- Redesigned Show and Movie pages

## 0.1.0 — July 11, 2026
### ✨ New
- First version: track shows and movies via TMDB
- Library, search, stats, and settings (French/English)
- Mark episodes watched, including in bulk per season

# NEXUS-9 — Level 3: The Servers

Flutter implementation of Level 3 ("The Servers") from the NEXUS-9 escape room project, a top-down, single-room puzzle level built for Android and iOS.

> This repository covers **Level 3 only**. NEXUS-9 as a whole is made up of 6 levels, each built by a separate team and integrated later into a single game.

## About This Level

Luna, a female Jack Russell Terrier, enters a room full of servers. An alarm triggers, and she must find three colored cables, read a riddle to deduce their correct order, and enter that sequence on a reset panel to restore the system and obtain Key 3.

Full design details, puzzle solutions, and user stories are documented in the [Wiki](https://github.com/EscapeRoomLevel3/scapeRoom_Level3/wiki).

## Tech Stack

| Area | Choice |
|---|---|
| Language / Framework | Dart + Flutter |
| State management | Provider |
| Local persistence | shared_preferences |
| Target platforms | Android, iOS |
| Version control | Git + GitHub |
| Task tracking | Jira (project `SCAP`) |
| Diagrams | draw.io |

## Getting Started

### Prerequisites

- [Flutter SDK](https://docs.flutter.dev/install) (stable channel)
- Android Studio (SDK + emulator, or a physical Android device)
- VS Code with the Flutter and Dart extensions
- Xcode on macOS (only required to build/run the iOS target)

### Setup

```bash
git clone https://github.com/EscapeRoomLevel3/scapeRoom_Level3.git
cd scapeRoom_Level3
flutter pub get
```

### Run

```bash
flutter run
```

Check that everything is set up correctly with:

```bash
flutter doctor
```

## Project Structure

```
lib/
 ├── main.dart              # Level3Entry — entry point for this level
 ├── ui/
 │   ├── screens/           # RoomScreen and its full-room states
 │   └── widgets/           # NotePopup, ResetPanelWidget, HUDWidget
 ├── logic/
 │   └── level_state.dart   # LevelState — cables, sequence, key status
 ├── models/
 │   ├── cable.dart
 │   ├── riddle_card.dart
 │   └── sequence_panel.dart
 └── services/
     └── save_service.dart  # Autosave and high score (shared_preferences)
assets/
 └── images/                # Room backgrounds, cable icons, UI elements
```

*(This structure follows the [Architecture Diagram](https://github.com/EscapeRoomLevel3/scapeRoom_Level3/wiki) — adjust as the implementation evolves.)*

## Git Workflow

**Branches**
- `main` — stable, protected. Nothing is pushed here directly.
- `develop` — integration branch for finished work.
- `feature/<short-name>` — one branch per task, created from `develop` (e.g. `feature/reset-panel-widget`).

**Commits**

Use the format:
```
<type>: <short description>
```
Types: `feat`, `fix`, `docs`, `refactor`, `test`, `chore`.

Examples:
```
feat: add cable tap detection in RoomScreen
docs: add class diagram to the wiki
fix: correct sequence validation order
```

**Pull Requests**
- Open a PR from your `feature/...` branch into `develop`.
- Reference the related Jira task in the description (e.g. `SCAP-12`).
- At least **1 approval** is required before merging.
- `develop` is merged into `main` only for stable, tested versions of the level.

## Team

| Name | Role | GitHub |
|---|---|---|
| Michael Isaza | Team Lead / Game Logic | [@MichaelIsaza](https://github.com/MichaelIsaza) |
| Santiago Galindo | UI/UX Developer | [@SANTIAGO-HERNANDEZ-1089](https://github.com/SANTIAGO-HERNANDEZ-1089) |
| Cristians Marmolejo | Game Logic Developer | [@CristiansMarmolejo2412](https://github.com/CristiansMarmolejo2412) |
| Samuel León | QA & Persistence | [@David-Leon1089](https://github.com/David-Leon1089) |

*Roles reflect each member's primary area of ownership in the code, all members rotate across Git/GitHub, documentation, and diagram tasks.*

## Links

- 📋 [Project Board (Jira – SCAP)](https://juanmontoya8109.atlassian.net/browse/SCAP)
- 📚 [Wiki](https://github.com/EscapeRoomLevel3/scapeRoom_Level3/wiki)
- 📝 [User Stories](https://github.com/EscapeRoomLevel3/scapeRoom_Level3/wiki/Stories-User)

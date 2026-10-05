<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/images/app-icon-readme-dark-v1.webp">
    <source media="(prefers-color-scheme: light)" srcset="assets/images/app-icon-readme-light-v1.webp">
    <img src="assets/images/app-icon-readme-light-v1.webp" width="96" alt="Firebase Remote Config app icon">
  </picture>
</p>

# Firebase Remote Config Flutter Application

[![Flutter](https://img.shields.io/badge/Flutter-3.0+-blue?style=for-the-badge&logo=flutter)](https://flutter.dev)
[![Firebase](https://img.shields.io/badge/Firebase-Latest-orange?style=for-the-badge&logo=firebase)](https://firebase.google.com)
[![Dart](https://img.shields.io/badge/Dart-3.0+-1f425f?style=for-the-badge&logo=dart)](https://dart.dev)
[![License: MIT](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

This project provides a production-ready implementation of Firebase Remote Config in Flutter, enabling dynamic control of application UI elements without requiring new app releases.

---

**Primary Applications:**
- A/B testing UI variations
- Feature flag management
- Real-time promotional content deployment
- Dynamic theming and branding

---

## Table of Contents

- [Demo](#demo)
- [Features](#features)
- [Installation](#installation)
- [Configuration](#configuration)
- [Project Structure](#project-structure)
- [Dependencies](#dependencies)
- [Testing and Validation](#testing-and-validation)
- [License](#license)
- [Author](#author)

---

## Demo

**Background Color Update**

<img src="https://raw.githubusercontent.com/lianeheidemann/firebase-remote-config-app/main/assets/gifs/gif1_cor_FirebaseRemoteConfig.gif" width="45%" alt="Background Color Update">

**Promotional Content Management**

<img src="https://raw.githubusercontent.com/lianeheidemann/firebase-remote-config-app/main/assets/gifs/gif2_propaganda_FirebaseRemoteConfig.gif" width="45%" alt="Promotional Content Management">

---

## Features

- **Remote background color** — the app background is driven by the `cor_fundo` parameter (hex color) fetched from Remote Config.
- **Remote promotional content** — the `propaganda` parameter switches between two bundled images (`propaganda.png` / `propaganda_alt.png`) without a new release.
- **Manual refresh** — an app bar action re-fetches and re-activates the latest configuration on demand.
- **Sane defaults & error handling** — local defaults are set before the first fetch, and fetch failures surface a retry screen instead of crashing.

---

## Installation

### System Requirements

- Flutter SDK 3.0 or higher
- Firebase CLI
- Android SDK
- Active Firebase project

### Setup Instructions

#### 1. Repository Setup
```bash
git clone https://github.com/lianeheidemann/firebase-remote-config-app.git
cd firebase-remote-config-app
```

#### 2. Dependency Installation
```bash
flutter pub get
```

#### 3. Firebase Setup

The repository ships with a sample `firebase_options.dart` and `android/app/google-services.json` for demonstration purposes only. To connect the app to **your own** Firebase project, regenerate both files with the FlutterFire CLI:

```bash
dart pub global activate flutterfire_cli
flutterfire configure
```

#### 4. Application Launch
```bash
flutter run
```

---

## Configuration

### Firebase Console Configuration

1. Navigate to Firebase Console → Remote Config
2. Select **Create Configuration**
3. Add parameters:

| Parameter  | Value       | Type   |
|------------|-------------|--------|
| cor_fundo  | #FF0000     | String |
| propaganda | alternativa | String |

4. Click **Publish Configuration**
5. Allow 5-10 seconds for propagation
6. Open the application and select the **Refresh** button

---

## Project Structure

```
firebase-remote-config-app/
├── lib/
│   ├── main.dart                    # Application entry point
│   └── firebase_options.dart        # Firebase configuration
├── android/
│   ├── app/
│   │   └── google-services.json     # Firebase credentials
│   └── build.gradle                 # Build configuration
├── assets/
│   ├── images/
│   │   ├── propaganda.png
│   │   └── propaganda_alt.png
│   ├── gifs/
│   │   ├── gif1_cor_FirebaseRemoteConfig.gif
│   │   └── gif2_propaganda_FirebaseRemoteConfig.gif
│   └── videos/
│       ├── video1_cor_FirebaseRemoteConfig.mp4
│       └── video2_propaganda_FirebaseRemoteConfig.mp4
├── pubspec.yaml                     # Dependencies
├── firebase.json                    # Firebase settings
└── README.md                        # Documentation
```

---

## Dependencies

**pubspec.yaml configuration:**

```yaml
dependencies:
  flutter:
    sdk: flutter
  firebase_core: ^4.10.0
  firebase_remote_config: ^6.5.2
  url_launcher: ^6.3.1
```

**Update dependencies:**
```bash
flutter pub upgrade
```

---

## Testing and Validation

### Local Testing Procedure

1. Execute `flutter run`
2. Open Firebase Console
3. Publish a new configuration
4. Select the **Refresh** button in the application
5. Verify the UI updates accordingly

---

## License

This project is licensed under the [MIT License](LICENSE).

---

<p align="center">Developed by <strong>Liane Heidemann</strong></p>

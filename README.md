# Firebase Remote Config Flutter Application

[![Flutter](https://img.shields.io/badge/Flutter-3.0+-blue?style=for-the-badge&logo=flutter)](https://flutter.dev)
[![Firebase](https://img.shields.io/badge/Firebase-Latest-orange?style=for-the-badge&logo=firebase)](https://firebase.google.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

Flutter app that demonstrates dynamic UI control with **Firebase Remote Config**: background color and promotional content update live, without a new release.

## Demo

<img src="https://raw.githubusercontent.com/lianeheidemann/firebase-remote-config-app/main/assets/gifs/gif1_cor_FirebaseRemoteConfig.gif" width="45%" alt="Background Color Update"> <img src="https://raw.githubusercontent.com/lianeheidemann/firebase-remote-config-app/main/assets/gifs/gif2_propaganda_FirebaseRemoteConfig.gif" width="45%" alt="Promotional Content Management">

## Features

- **`cor_fundo`** — hex color that sets the app background.
- **`propaganda`** — switches between two bundled promo images.
- **Refresh button** — re-fetches and re-activates config on demand.
- Local defaults + retry screen if a fetch fails.

## Getting Started

```bash
git clone https://github.com/lianeheidemann/firebase-remote-config-app.git
cd firebase-remote-config-app
flutter pub get
```

The repo ships with a sample `firebase_options.dart` and `google-services.json` for demo purposes. To use your own Firebase project, regenerate them with:

```bash
dart pub global activate flutterfire_cli
flutterfire configure
```

Then run the app:

```bash
flutter run
```

## Configuring Remote Config

In **Firebase Console → Remote Config**, add these parameters and publish:

| Parameter  | Value       | Type   |
|------------|-------------|--------|
| cor_fundo  | #FF0000     | String |
| propaganda | alternativa | String |

Open the app and tap **Refresh** to see the change (propagation takes a few seconds).

## License

[MIT](LICENSE) © [Liane Heidemann](https://github.com/lianeheidemann)

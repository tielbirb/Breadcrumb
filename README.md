<p align="center">
  <img src="logo_512.png" width="160" alt="Breadcrumb logo">
</p>

<h1 align="center">Breadcrumb</h1>

<p align="center">
  A <a href="https://github.com/FWGS/xash3d-fwgs">Xash3D FWGS</a> fork built exclusively for <b>Sven Co-op</b>.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/license-GPL--3.0-6B4226" alt="License">
  <img src="https://img.shields.io/badge/platform-Android-6B4226" alt="Platform">
  <img src="https://img.shields.io/badge/game-Sven%20Co--op-6B4226" alt="Game">
</p>

---

## About

Breadcrumb is a Sven Co-op-focused build of the Xash3D FWGS engine, packaged as an Android app.
Support for other GoldSrc games (Half-Life, Counter-Strike, etc.) is **not** a goal of this project.

## Status

Early scaffold. The launcher works; the engine is not wired in yet (see [Engine build](#engine-build)).

## Project layout

```
.github/        CI workflow, issue and PR templates
app/            Android app (launcher + engine host)
assets/         Logo (brown recolor of the Xash3D FWGS logo)
engine/         Xash3D FWGS fork (git submodule)
```

## Getting started

```sh
git clone --recurse-submodules https://github.com/tielbirb/breadcrumb.git
cd breadcrumb
gradle wrapper --gradle-version 8.7   # one time, generates ./gradlew
./gradlew assembleDebug
```

The APK is written to `app/build/outputs/apk/debug/`.
Every push to `main` also builds an APK via GitHub Actions (see the **Actions** tab).

## Engine build

1. Build the engine in `engine/` for Android (`arm64-v8a`, `armeabi-v7a`), including SDL2.
2. Copy the resulting `.so` files into `app/src/main/jniLibs/<abi>/`.
3. Connect `EngineActivity` to SDL's activity and launch with `-game svencoop`.

## Game files

Breadcrumb does **not** include any game data. Copy your own `svencoop` (and `valve`)
folders into the folder shown on the launcher screen:

```
Android/data/io.github.breadcrumb/files/
```

## Contributing

Pull requests are welcome, as long as they target Sven Co-op. Changes that add support
for other games won't be merged.

## Credits

- [Xash3D FWGS](https://github.com/FWGS/xash3d-fwgs) by the FWGS team
- Xash3D originally created by Unkle Mike
- Sven Co-op is a trademark of its respective owners. Breadcrumb is not affiliated with or endorsed by them.

## License

GPL-3.0, same as upstream. See [LICENSE](LICENSE).logoogo

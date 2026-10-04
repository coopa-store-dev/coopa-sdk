<p align="right">
  <strong>English</strong> · <a href="README.zh_CN.md">简体中文</a>
</p>

# Coopa SDK

The SDK for making Coopa card games: public headers, the prebuilt card shell (web and ESP32-C3), the font, and the `coopa` command. Download it from [Releases](https://github.com/coopa-store-dev/coopa-sdk/releases/latest) (`coopa-sdk.tar.gz`).

Most developers never install it by hand: the [game template](https://github.com/coopa-store-dev/coopa-game-template) sets it up in Codespaces.

## Commands

| Command | What it does |
|---|---|
| `coopa rename <id>` | Rename the game (files, C name prefix, save namespace, `coopa.toml`) |
| `coopa run` | Build the web version and play it in the browser |
| `coopa check` | Run the same check as the store (card part needs ESP-IDF v5.5.3) |
| `coopa version` | Show the SDK version |

Needs Emscripten 6.0.11 (the `emscripten/emsdk:6.0.11` image) and Python 3.11 or newer.

## Versions

Every card shell upgrade publishes a new SDK. A game's `coopa.toml` says which SDK it needs (`sdk = N`); the check reports a game that needs a newer SDK.

## Licenses

See `licenses/` in the SDK: LVGL, ESP-IDF and Espressif components, and the Fusion Pixel font (SIL OFL 1.1).

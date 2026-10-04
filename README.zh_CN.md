<p align="right">
  <a href="README.md">English</a> · <strong>简体中文</strong>
</p>

# Coopa SDK

给 Coopa 卡做游戏的 SDK:公开头文件、编好的卡外壳(网页版和 ESP32-C3 卡上版)、字体、`coopa` 命令。在 [Releases](https://github.com/coopa-store-dev/coopa-sdk/releases/latest) 下载 `coopa-sdk.tar.gz`。

大多数开发者不用自己装:[游戏模板](https://github.com/coopa-store-dev/coopa-game-template)在 Codespaces 里会装好。

## 命令

| 命令 | 做什么 |
|---|---|
| `coopa rename <id>` | 给游戏改名(文件名、C 名字前缀、存档命名空间、`coopa.toml`) |
| `coopa run` | 编网页版,在浏览器里玩 |
| `coopa check` | 跑和商店一样的检查(卡上版部分要 ESP-IDF v5.5.3) |
| `coopa version` | SDK 版本 |

要 Emscripten 6.0.11(镜像 `emscripten/emsdk:6.0.11`)和 Python 3.11 以上。

## 版本

卡的外壳每升级一次就发一版 SDK。游戏的 `coopa.toml` 写着要哪一版(`sdk = N`);要的 SDK 比装的新,检查会报出来。

## 发布新版(店主)

在外壳仓库(私有)里:改 `sdk/VERSION` → 提交 → `. ~/esp/esp-idf-v5.5.3/export.sh` → `tools/sdk_release.sh` → `tests/sdk_e2e.sh build-sdk/coopa-sdk` 和 `tests/sdk_samples.py build-sdk/coopa-sdk` 都过 → 上传:

```bash
gh release create vN build-sdk/coopa-sdk.tar.gz build-sdk/coopa-sdk.tar.gz.sha256 -R coopa-store-dev/coopa-sdk --title "SDK N"
```

## 许可证

见 SDK 里的 `licenses/`:LVGL、ESP-IDF 和乐鑫组件、Fusion Pixel 字体(SIL OFL 1.1)。

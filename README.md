# VRM Character Sheet Exporter

VRM ファイルをブラウザで読み込み、決まった構図（全身 正面／側面／背面、胸上、顔 正面、顔 斜め）を高解像度 PNG で書き出すツールです。
AI 画像生成・動画生成にキャラクターの参照画像（キャラクターシート）を渡すために作りました。

A browser tool that loads a VRM file and exports fixed-composition character sheets (full body front / side / back, bust, face front, face 3/4) as high-resolution PNGs — handy as reference images for AI image / video generation.

## 使い方 / Usage

1. `index.html` をブラウザで開く（GitHub Pages で公開している場合はそのURL）
2. VRM ファイルをドロップ、またはファイル選択で読み込む
3. 構図プリセットを選ぶ。必要ならカメラ（向き・見下ろし・距離・高さ・画角）と表情を調整
4. 出力サイズ・背景・ファイル名を決めて「PNGを保存」。「6構図をまとめて保存」で全プリセットを一括保存

- 保存時は指定サイズ（既定 1536×2048）で描き直すので、画面の大きさに関係なく高解像度で出力されます
- 背景は 透明 / 薄い灰色 / 白 / グリーン から選べます
- ファイルはすべてブラウザ内で処理され、サーバーには送信されません

1. Open `index.html` in a browser (or the GitHub Pages URL)
2. Drop a `.vrm` file or pick it with the file input
3. Choose a composition preset; fine-tune the camera (yaw / pitch / distance / height / FOV) and expression if needed
4. Set output size, background and file name, then **Save PNG**. **Save all 6 presets** exports every preset at once

The image is re-rendered at the requested size (default 1536×2048) on save, so output resolution does not depend on the window size. Everything runs locally in the browser; nothing is uploaded.

## 技術 / Tech

- [three.js](https://threejs.org/) 0.160.0
- [@pixiv/three-vrm](https://github.com/pixiv/three-vrm) 2.1.0
- 単一の HTML ファイル。ライブラリは jsDelivr の importmap から読み込み（ビルド不要）

## 対応 / Supported

- VRM 0.x / VRM 1.0（VRM 0.x は自動で正面向きに補正）
- モダンブラウザ（Chrome / Edge / Firefox / Safari）

## ライセンス / License

MIT

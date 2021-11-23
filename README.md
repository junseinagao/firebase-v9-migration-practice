# Firebase V9 App

このレポジトリは、Firebase v8 から v9 へのマイグレーションを経験するための練習レポジトリです。

# Setup

## VS Code settings

VS Code の Live Share を使うことを想定しています。

VS Code 拡張機能の Vetur をワークスペースで Off にして、Volar をインストールしてワークスペースで有効にしてください。

Vetur -> 「ワークスペースで無効」
Volar -> 「ワークスペースで有効」

## lanch up local server

```bash
$ npm ci
$ npm run serve
```

# Todo

1. `firebase/compat/app`を使用して v8 の記述を残しつつマイグレーションする。
2. モジュールスタイルにリファクタリングする

- `src/firebase.js` を更新する
- v9 の firestore を使用する

## 参考

[バージョン 8 からモジュラー WebSDK にアップグレードします](https://firebase.google.com/docs/web/modular-upgrade)

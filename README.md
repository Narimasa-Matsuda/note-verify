# note-verify

note 記事に載せる **HTML / CSS / JS の動作確認**用プロジェクト。ビルド不要・基本HTMLファイルだけ。

## 構成

```
note-verify/
├── index.html      … 検証ページの一覧（リンク集）
├── demos/          … 検証ページを置く場所
│   └── sample.html … 動作確認用サンプル（ボタン+カウンター）
└── README.md
```

## 使い方

### そのまま開く
`index.html` をブラウザにドラッグ&ドロップ、またはダブルクリック。多くの確認はこれで十分です。

### ローカルサーバで開く（推奨）
`fetch` / モジュール / 一部の JS は `file://` だと制限があるため、サーバ経由が確実です。

```bash
cd ~/Projects/note-verify
python3 -m http.server
# → http://localhost:8000/ をブラウザで開く
```

## 新しい検証を追加する

1. `demos/` に HTML を1ファイル追加（`sample.html` をコピーして書き換えるのが早い）。
2. `index.html` の `DEMOS` 配列に1行足す：
   ```js
   { file: "demos/あなたのファイル.html", name: "タイトル", desc: "説明" },
   ```
3. `index.html` を再読み込みすると一覧に出ます。

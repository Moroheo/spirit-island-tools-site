# スピリットアイランド・ツール

スピリットアイランド（ボードゲーム版）用の非公式ヘルパー。精霊力トラッカー、精霊ごとの基本プレイ方針とカードTier表、敵対国の達成チェッカー、ルールブック／FAQ を収録。

ビルド不要の単一ページアプリで、React と Babel を CDN から読み込み、ブラウザ上で JSX を変換して動く。データはブラウザの localStorage に保存されるので、同じ端末・同じブラウザなら次に開いても残る。

## GitHub Pages で公開する手順

1. GitHub で新しいリポジトリを作る（例：`spirit-island-tools`）。Public にする。
2. このフォルダの中身をすべてアップロードする。
   - ブラウザから：リポジトリの **Add file → Upload files** に、この `spirit-island-site` フォルダの中身（`index.html` など）をドラッグしてコミット。
   - フォルダごとではなく「中身」を置く。`index.html` がリポジトリの直下に来るようにする。
3. リポジトリの **Settings → Pages** を開く。
4. **Build and deployment** の Source を **Deploy from a branch** にする。
5. Branch を **main**、フォルダを **/(root)** にして **Save**。
6. 1〜2分待つと、同じ Pages 画面の上部に公開 URL（`https://<ユーザー名>.github.io/spirit-island-tools/`）が出る。

## スマホでアプリのように使う

公開 URL をスマホのブラウザで開き、共有メニューから「ホーム画面に追加」。全画面で開き、オフラインでも起動する（サービスワーカーがキャッシュする）。

## 中身を編集したいとき

- 文言やデータは `app.jsx` を直接書き換える。ビルドは不要で、コミットすればそのまま反映される。
- 見た目のクラスは `styles.css` に自前で定義してある（Tailwind は使っていない）。
- 内容を更新したら `sw.js` の `CACHE` の名前（`si-tools-v1`）を `v2` などに上げると、古いキャッシュが確実に置き換わる。

## ファイル構成

- `index.html` — 読み込みの入口
- `app.jsx` — アプリ本体
- `styles.css` — 最小限のユーティリティCSS
- `manifest.webmanifest` — ホーム画面追加用の設定
- `sw.js` — オフライン用サービスワーカー
- `icon-192.png` / `icon-512.png` / `icon-180.png` — アイコン

## 注意

このアプリは非公式のファンメイド。ゲームの権利は Greater Than Games に帰属する。カードの評価や方針は個人の見解を含む。

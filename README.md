# GTNET 電子領収書 お客様ページ（静的ページ）

お客様がQRコード・メールのリンクから開く「領収書・請求書のご確認」ページです。
GitHub Pages で配信し、データは電子領収書システム（GAS・外部公開デプロイ）から `fetch` で受け取ります。

- 本体のシステム：`gtnet-systems/receipt-nippo-system`（非公開）。API は `src/31_public_api.js`
- 移した理由：Android の Chrome が `script.google.com/…/exec` に `/u/N/` を差し込み、開けなくなるため（2026-09-23）
- URL の形：`https://gtnet-systems.github.io/（このリポジトリ名）/?token=（トークン）`

## 注意（公開リポジトリ）

- 鍵・シートID・個人情報は置かない。置いてよいのは、すでにQRで公開している `/exec` のURLだけ
- `fetch` に `credentials` を付けない。POST の `Content-Type` は `text/plain`
- GAS 側の更新は「デプロイを管理 → 鉛筆 → 新バージョン」。「新しいデプロイ」は使わない（`/exec` が変わる）

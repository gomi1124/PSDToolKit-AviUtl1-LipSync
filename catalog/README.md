# AviUtl2カタログ登録資料

`registration.json`は、AviUtl2カタログv0.3.3の「パッケージ登録」画面にあるJSON入力へ貼り付けるためのフラット形式データです。

カタログ側で移行中のsource bundle形式は、安定版アプリが正式対応するまで使用しません。登録時は必ず公式Latestのアプリを確認し、v0.3.3ではこのファイルをそのまま使用してください。

`installer.source.direct: null`は、v0.3.3の新規登録で既定の直接URL設定を消し、GitHub Release設定を選択させるために必要です。JSON入力から削除しないでください。

画像は登録用JSONに外部URLを設定せず、カタログ画面から次のローカルファイルを添付してください。

- サムネイル: `images/thumbnail.png`（206x206）
- 説明画像: `images/detail.png`（1280x720）

送信後のPRでは、カタログデータリポジトリの`image/`配下に画像が追加され、`index.json`から`./image/...`で参照されることを確認してください。

インストーラーにはGitHub Releasesの`.au2pkg.zip`を指定しています。バージョン検出対象は`LipSyncAviUtl1.mod2`です。新しいバージョンを公開するときは、`latest-version`と末尾のバージョン要素にあるリリース日・バージョン・XXH3-128を更新してください。

画像の再生成にはPillowが必要です。

```powershell
py -3 .\catalog\generate_assets.py
```

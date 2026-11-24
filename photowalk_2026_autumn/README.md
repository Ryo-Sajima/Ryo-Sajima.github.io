# PhotoWalk 投票結果ページの年次更新

毎年の更新は、基本的に `event-data.json` だけを編集します。

## 更新する場所

- `event.clubName`: 写真部名
- `event.eventName`: イベント名
- `event.date`: 開催日
- `event.voters`: 投票者数
- `event.totalVotes`: 総投票数
- `event.galleryUrl`: 投票対象写真一覧のURL
- `event.contactEmail`: 得票数問い合わせ先
- `event.pointSystem`: 順位ごとの付与ポイント
- `entries`: 各受賞写真の順位、氏名、得票数、ポイント、画像ファイル名
- `galleryGroups`: 4位など、横並びでまとめたい順位のグループ

日本語と英語の表記は、`ja` と `en` の両方を更新してください。

## 写真の追加

1. 画像ファイルをこのフォルダーへ追加します。
2. `entries` に1件追加します。
3. `image` に画像ファイル名を指定します。

例:

```json
{
  "rank": 1,
  "name": { "ja": "写真 太郎", "en": "Taro Shashin" },
  "votes": 12,
  "points": 48,
  "image": "1_写真太郎_1.jpg"
}
```

## 表示の確認

`event-data.json` はWebサーバー経由で読み込まれます。ローカルで確認する場合は、このフォルダーで次を実行してください。

```powershell
python -m http.server 8000
```

次にブラウザーで `http://localhost:8000/` を開きます。

`index.html` を直接ダブルクリックして開いた場合は、ブラウザーのセキュリティ制限によりJSONを読み込めません。必ずローカルWebサーバーまたはGitHub Pages経由で開いてください。

# ゲンバカエル LP

建築・土木の施工管理技術者向けの求職者LP（ホワイト度チェック → LINE登録）。

## 公開前に設定するもの（index.html）
- `LINE_URL`：LINE公式アカウントの友だち追加URL（https://lin.ee/...）
- `window.GA_ID`：GA4の測定ID（G-XXXXXXXXXX）。空なら計測タグは読み込まない
- フッターの運営会社名・有料職業紹介事業の許可番号
- 準備が整ったら `<meta name="robots" content="noindex">` を削除

## 計測イベント（dataLayer / GA4）
- `job_select`：職種の切り替え（job）
- `check_start`：診断の最初の回答（job）
- `check_complete`：判定（job, level A〜D, white_score, age）
- `line_click`：LINEボタンのクリック（position, job, level）
- `code_copy`：合言葉（判定A〜D）のコピー（level）

## 内部アクセスの除外
- `https://genbakaeru.github.io/?internal=1` を一度開くと、そのブラウザは「内部」として記録される（画面右上に「内部アクセス（GA除外）」と表示）
- 以後のアクセスはGA4に `traffic_type=internal` 付きで送られ、GA4の「内部トラフィック」データフィルタで除外できる
- 解除は `https://genbakaeru.github.io/?internal=0`
- ブラウザごと・端末ごとに1回必要（LINEアプリ内ブラウザも別扱い）

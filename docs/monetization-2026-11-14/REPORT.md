# sleep-guide 収益化改善報告（2026年11月14日）

作業ブランチ：`improve/monetization-2026-11-14`。mainへのマージ・本番公開は未実施です。
既存サイトの修正です。公開中のデザイン、広告コード、Tracking ID、解析IDを保持。順位・AIO引用・成果発生は検証できていません。

## 優先問題と変更

S・Mサイズ・洗濯の2記事を充実。寸法・重量差を比較表にし、寝床から洗濯・干し場所までの確認順序を具体化。既存のA8販売案内と関連記事を維持。

サイズ比較は既存確認値を使い、購入直前に公式の利用対象・洗濯・返品条件を読む流れへ補強。A8広告HTMLは改変していません。

## 本文を充実した既存記事

文字数はHTMLからscript/styleと空白を除いた概算で、評価指標ではありません。文字数のための水増しはしていません。

| 記事（公開ディレクトリからの相対パス） | 本文概算・改善前 → 改善後 |
| --- | --- |
| `hugravi-weight-wash.html` | 1659 → 2029 |
| `hugravi-size-choice.html` | 774 → 1454 |

パンくずを追加した記事は、その表示内容に合うBreadcrumbListを設定。既存のArticleとcanonicalは照合済みです。架空のReview・AggregateRating・Offerは新設していません。購入者レビュー10本文以上を個別確認できた商品は0件で、レビュー要約は追加していません。価格・仕様の古い確認日を一律に新しくしていません。

## 検証結果

- 静的検証：7ページ（404含む）、エラー0。タイトル・description・h1、canonical、サイトマップ、内部リンク・アンカー・参照資産、JSON-LD、重複タイトル・canonical、トップからの到達性を点検。
- サイトマップ：4URL。noindexとの整合を検証。robots.txtは既存のクロール許可と本番Sitemap指定を維持。
- ブラウザ：360・390・1440pxの21ケース。ページ横はみ出し0。外部広告・解析への通信は遮断。画像の実配信や計測通信の成功を意味しません。
- 改善前の横はみ出し：0ケース → 改善後0ケース。
- 広告保全：リンク・広告画像のHTML断片17個をSHA-256照合、一致。`scripts/affiliate-baseline.json`が修正前の基準です。既存Tracking ID：moon12-22。
- 外部参照先：2URLをHTTP GETで点検。未確認・差し替え前404を含む応答記録は`external-links.json`参照。403/503はリンク切れと断定しません。
- 公開状態：本番の既存ページ・robots・sitemapは200、無効URLは404。ブランチの改善は本番未反映です。
- 表示速度：メダカでは外部画像6リクエストを除去。他サイトを含む本番CWV・Lighthouse・実ユーザーLCP/INP/CLSは未測定。高速化の数値効果は主張しません。

静的HTMLサイトのためビルド工程はありません。

## 未確認事項・公開前の判断

洗濯機の容量表示だけでは適合を断定できません。実機使用・使用感・医療効果・購入者レビューは未検証。既存Amazonリンクの商品一致も未確認で、新設・書換えなし。about/privacyの既存noindexは維持。

共通：Amazonの商品ページの現在の表示・レビュー本文10件、A8管理画面の提携・成果対象・掲載URL、Search Consoleのクエリ別表示回数・CTR・順位、Cloudflare実測速度、実際の成果計測は未確認。広告をテスト購入・申込する検証は行っていません。既存の商品画像は、A8バナー・イメージ・メーカー参照を区別。新しい未許諾写真を追加していません。

## 全ページの診断台帳

`page-audit.json`にtitle/h1/description/canonical・index可否・サイズ・リンク数・構造化データ・到達性を保存。全ページに一律のタイトル変更はせず、検索意図が重なる販売年違いを区別し、問題のある記事とUIを優先しました。トップから到達できないindex許可ページ・内部リンク切れ・完全なタイトル重複は検証後0件。記事の統合・削除はしていません。

| ページ | 検索設定 | 本文概算 | 内部リンク先数 | 広告リンク・画像数 | 構造化データ |
| --- | --- | ---: | ---: | ---: | --- |
| `about.html` | noindex | 336 | 3 | 0 | AboutPage |
| `hugravi-weight-wash.html` | index許可 | 2029 | 5 | 7 | Article, FAQPage, BreadcrumbList |
| `hugravi-size-choice.html` | index許可 | 1454 | 5 | 3 | Article, BreadcrumbList |
| `index.html` | index許可 | 907 | 6 | 6 | WebSite |
| `weighted-blanket-checklist.html` | index許可 | 1236 | 6 | 2 | Article, BreadcrumbList |
| `404.html` | noindex | 63 | 1 | 0 |  |
| `privacy.html` | noindex | 418 | 3 | 0 | WebPage |

## 再実行・差分の確認

- `python scripts/check_site.py .`（Python標準ライブラリのみ）
- 全差分：`git diff main...improve/monetization-2026-11-14`
- 本番へのマージ・デプロイは別途承認後。プレビュー環境が自動生成されても本番とは区別。
- 公開後はcanonical・サイトマップの実応答、Search Consoleの除外理由、記事→広告クリック→成果を確認。変更前後で同じ期間・クエリを比較してください。

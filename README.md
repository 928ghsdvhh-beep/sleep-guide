# 眠りの選択眼

対象商品: ハグラビ

公開方式: GitHub main → Cloudflare Pages（既存 medaka-guide と同じ静的HTML方式）。Cloudflareへの接続は別途必要。

## 公開前チェック
- 正式サイト名・独自性と商標の確認
- メーカー仕様・価格・ASP提携条件の確認
- 購入者レビュー10件以上確認できた場合だけ良い点・悪い点を要約
- 商品写真の権利確認、実機未使用なら使用体験を捏造しない
- AmazonはASIN照合済みの商品ページとレビューへの2リンクを隣接表示。ID moon12-22。未照合ならリンク保留
- ASPの広告表示、sponsored/nofollow、検索流入測定
- 記事完成後にnoindexを解除し、robots.txtとsitemap.xmlを公開URLに合わせて更新

現在は公開準備用のnoindexページです。

## Cloudflare Pages 公開URL（2026-11-10確認）
- プロジェクト: `sleep-guide`
- URL: https://sleep-guide.pages.dev
- Cloudflare管理画面のプロジェクト一覧スクリーンショットで確認済み。
- デプロイ履歴あり。HTTPアクセス・表示動作・検索公開状態は別途検証する。

## 2026-11-11 SEO・AI検索点検（最新状態）

- mainの公開用HTMLは検索許可済み。上記の公開準備中・noindex維持の記録は過去の状態。個別ページのnoindexは別途判断し、今回解除していない。
- canonicalとサイトマップをCloudflare Pagesの拡張子なしURLに統一。本文と整合するArticle/WebSite/WebPage構造化データを整備。架空の評価・日付は追加していない。
- 404.htmlを設置し、存在しないURLがトップページ扱いになる動作を防止。広告コードは保持。
- Google登録・AI検索への引用は未確認。公開反映は別途確認する。

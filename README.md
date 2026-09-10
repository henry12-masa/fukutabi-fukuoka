# ふくたび福岡（福岡観光ポータルサイト）

福岡（博多・天神・大濠・太宰府）の観光スポット・グルメ情報を集約した静的HTMLポータルサイト。新幹線・航空券は楽天トラベル／じゃらん／Skyscanner／JR公式への外部リンクで連携。沖縄版「しまたび沖縄」・京都版「ことたび京都」の姉妹サイト。

- 公開URL: https://fukutabi-fukuoka.napoblog.com
- GitHub: https://github.com/henry12-masa/fukutabi-fukuoka
- ホスティング: Cloudflare Pages（GitHub連携で自動デプロイ、main pushで反映）

## 構成

```
fukuoka_portal/
├── index.html        トップページ（エリア紹介・人気スポット/グルメのピックアップ）
├── spots.html         観光スポット一覧（エリア別フィルタ付き）
├── restaurants.html   グルメ一覧（ジャンル別フィルタ付き）
├── transport.html     新幹線・航空券比較ページ
├── privacy.html        プライバシーポリシー
├── css/style.css      共通スタイル（博多祇園山笠をイメージした藍・朱色・金基調）
├── js/main.js         モバイルナビ／絞り込みフィルタ／航空券検索リンク生成
├── favicon.svg         提灯（ちょうちん）アイコン
└── images/             SVGイラスト25点（スポット14・グルメ11） + OGP画像
```

## ローカルで確認する方法

`note/.claude/launch.json` に `fukuoka-portal` サーバー設定を追加済み。Claude Codeのプレビュー機能、または以下で確認できる。

```bash
python -m http.server 8836 --directory fukuoka_portal
```

## アフィリエイトについて

- **楽天トラベル**: 設定済み。航空券（`travel.rakuten.co.jp/air/domestic.html`、沖縄版・京都版と共通リンク）と、福岡行きJR楽パック（`travel.rakuten.co.jp/package/jr/hotel_list/cnt_japan/sub_fukuoka_prefecture/`専用リンク）の2種類。
- **じゃらん（A8.net）**: 設定済み。航空券（`jalan.net/airticket/`、沖縄版・京都版と共通リンク）と、JR新幹線+宿パック（`jalan.net/dp/jr/`専用リンク、京都版と共通）の2種類。
- **Skyscanner**: アフィリエイト登録不要な検索結果ディープリンク形式（福岡空港 FUK 向け）。
- 全リンクとも実際にアクセスして遷移を動作確認済み（2026-09-10）。福岡県のRakuten Travel JRパッケージURLは `sub_fukuoka` ではなく `sub_fukuoka_prefecture` が正しいスラッグ（UI経由のキーワード検索で確認）。

## 今後の拡張候補

- 掲載スポット・グルメの実写真（現状はSVGイラスト）
- Google Search Console登録
- 独自ドメインのSSL反映確認（napoblog.comのワイルドカードゾーンにサブドメイン追加）

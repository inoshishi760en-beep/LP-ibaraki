# 茨城旅行LP（MVP）

単一HTML（Tailwind CDN）で構成した茨城観光訴求用ランディングページです。モバイル優先・高速表示・読みやすさを重視しています。

- 主要ファイル: `docs/index.html`
- 画像: 外部（Unsplash）の著作権フリー画像URLを使用

## ローカルプレビュー方法

最も簡単な方法は、`docs/index.html` をブラウザで直接開くことです。

1. このフォルダを開く
2. `docs/index.html` をダブルクリック（既定ブラウザで開く）

開発者向けに簡易HTTPサーバーでのプレビューも可能です（任意）。

- macOS/Linux: `python3 -m http.server 8080` → `http://localhost:8080/docs/`
- Windows (PowerShell): `python -m http.server 8080` → `http://localhost:8080/docs/`

## 画像の差し替え方法

本LPは Unsplash の外部画像URLを使用しています。`index.html` 内にURLとキーワードのコメントを残しています。

1. `index.html` をテキストエディタで開く
2. 差し替えたい `<img>` の `src` / `srcset` または Hero 背景の `background-image` を任意のURLに変更
3. 可能であれば `srcset`/`sizes` を維持（レスポンシブ品質向上のため）
4. `alt` も内容に合わせて更新（アクセシビリティ）

ヒント（キーワード例）

- Ibaraki, Hitachi Seaside Park, Nemophila, Kochia
- Fukuroda Falls, Oarai Shrine, Mount Tsukuba, Ibaraki coast

## カラー/コピーの差し替えポイント

- カラーは Tailwind のクラスで指定しています。
  - 主色（茨城の海の青）: `bg-blue-800` / `text-blue-800`（#1e40af）
  - アクセント（新緑の緑）: `bg-green-600`（#16a34a）
  - サブ（水色）: `text-sky-400` / `bg-sky-50`（#38bdf8）
  - 背景ライト: `bg-slate-50`（#f1f5f9）
  - 文字ダーク: `text-slate-900`（#0f172a）
- コピー（テキスト）は `index.html` 内の該当セクション（Hero/見どころ/モデルコース/アクセス/FAQ/CTA）を直接編集してください。

## 外部リンクの更新注意

- 公式サイトや交通情報は、最新の情報に変動します。リンク先の時刻・料金・開催状況などは必ず最新をご確認ください。
- CTAの予約ボタンは仮リンク（例：じゃらん）です。運用時には自社/提携先の予約ページや問い合わせフォームに差し替えてください。

## 技術メモ（MVP範囲）

- Tailwind CDNを使用し、フレームワークやビルド工程は不要
- 画像は `loading="lazy"`、Heroは `background-image`、`srcset`/`sizes` で品質と軽快さを両立
- ナビはページ内アンカー＋スムーズスクロール。スクロール時にヘッダーが半透明→ソリッドに変化
- Heroのフェードイン・カードのホバー浮き上がりを軽微なアニメーションで表現
- OGP/Twitterカードのメタを設定（画像URLは仮）
- 簡易のクッキーバナー風トーストを実装（文言のみ、`localStorage` で閉じる状態を記録）

## セクション構成

1. ヘッダー（固定）
2. ヒーロー（FV）
3. 見どころ（4カード）
4. モデルコース（日帰りの例）
5. アクセス（概略とGoogleマップ）
6. FAQ（Q&A 4項目）
7. CTA（再掲）
8. フッター（コピーライト/簡易リンク/SNSアイコン）

## ライセンス/クレジット（画像）

- 画像は Unsplash からの外部リンクを仮使用しています。運用時は各画像の利用条件を確認し、必要に応じてクレジット表記や差し替えをご検討ください。

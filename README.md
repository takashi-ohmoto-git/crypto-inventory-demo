# Crypto Inventory — Live Demo

**https://takashi-ohmoto-git.github.io/crypto-inventory-demo/**

実ネットワークを Zeek で受動観測し、いま実際に使われている暗号を棚卸しして
耐量子暗号 (PQC) 移行に必要な数字を出すツールのダッシュボードです。
このリポジトリは**デモの配信用**で、ビルド済みの静的ファイルのみを置いています。
ソースコードは含みません。

> **EN** — Live demo of Crypto Inventory, a passive cryptographic inventory built on Zeek.
> This repository hosts the built dashboard only; it contains no source code.

## データについて

表示されるデータは実測値ですが、**公開前に匿名化しています**。

- 伏せた項目: エンドポイントの IP アドレス / SNI・サーバ名 / リーフ証明書のサブジェクト /
  証明書のフィンガープリント / 資産 ID / 取り込み元のログ名
- 方式: 実行ごとのランダム鍵による HMAC-SHA256。鍵は保存していないため、
  生成した側も含め誰も元の値に戻せません。
- 残した項目: 証明書の発行者 (CA) 名、ポート番号、観測時刻、アルゴリズム、
  分類、カバレッジ、集計値のすべて。CA 名は「どの CA が弱い証明書を出しているか」の
  分析に必要で、観測側を特定しないため保持しています。

詳細は画面内の「匿名化」表示を参照してください。

## 収録内容

| ファイル | 内容 |
| --- | --- |
| `index.html` / `assets/` | ダッシュボード (React + TypeScript) |
| `report.json` | 解析結果。ダッシュボードが読み込む |
| `cbom.json` | CycloneDX 1.6 形式の CBOM。画面からは参照しない |

規模: 3 ソース / 775 観測 / 388 エンドポイント / 1947 資産 / 96 証明書。

## 注意

移行期限は NIST IR 8547 Initial Public Draft (2024-11) に基づく暫定値です。
2026-08 時点で最終版は公開されておらず、年限・条件が変更される可能性があります。
確定した規制要件として扱わないでください。

---

© 2026 Takashi Ohmoto. All rights reserved.
デモ閲覧用に公開しているものです。オープンソースとしての利用許諾は行っていません。

# azn-llmo-dashboard

IDEA LLMO ダッシュボード（Monitoring / Strategy）の公開用リポジトリ。

## 公開URL

| | URL |
|---|---|
| ランディング | https://hibiki-nabetani-ideatech.github.io/azn-llmo-dashboard/ |
| Monitoring | https://hibiki-nabetani-ideatech.github.io/azn-llmo-dashboard/monitoring |
| Strategy | https://hibiki-nabetani-ideatech.github.io/azn-llmo-dashboard/strategy |

## アクセス

3ページはいずれも **パスワード保護** されています。
ページ本体を **AES-256-GCM**（鍵導出は PBKDF2-HMAC-SHA256 / 310,000回）で暗号化しており、
正しいパスワードを入力するまでソースからも内容は読み取れません。
復号はブラウザの WebCrypto で行うため外部ライブラリは不要です。

パスワードは別途お伝えします。同一ブラウザでは初回入力のみで、以降は再入力なしで
Monitoring / Strategy を行き来できます（「このブラウザに記憶する」をオフにした場合は
タブを閉じるまで保持）。

検索エンジンからは `robots.txt` と各ページの `noindex` で除外しています。

## このリポジトリに含めていないもの

本リポジトリは **公開ページ（暗号化済みHTML）のみ** を置いています。
以下はリポジトリに含めていません（暗号化の意味がなくなるため）。

- 暗号化前の平文HTML
- 生成パイプライン（`_pipeline/`：Brand Radar のパース、診断結果、ペルソナ分析、一次情報リサーチ）
- 詳細レポート

これらは別途 zip でお渡ししています。月次更新時はその zip 内の `_pipeline/build_all.sh` を
実行して生成された 3ファイル（`index.html` / `monitoring/index.html` / `strategy/index.html`）を
本リポジトリに上書きコミットしてください。

## 構成

```
index.html              ランディング（Monitoring / Strategy への入口）
monitoring/index.html   Dashboard / Monitoring
strategy/index.html     Dashboard / Strategy
robots.txt              検索エンジン除外
```

すべて外部依存なしの単一HTMLです（Chart.js もインライン埋め込み済み）。

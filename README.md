# 永井陽斗 / Haruto Nagai — 個人サイト

大阪大学 原田研究室（M2）の永井陽斗の個人 Web サイトのソースコードです。
ロボット・組立順序計画に関する研究内容、業績、ブログなどを掲載しています。

🌐 **公開サイト:** <https://n-haru0524.github.io/web/>

## 概要

- [Jekyll](https://jekyllrb.com/) による静的サイトです。
- デザインは [al-folio](https://github.com/alshedivat/al-folio) テーマをベースにカスタマイズしています。
- GitHub Pages でホスティングしています。

## ディレクトリ構成（主なもの）

| パス | 内容 |
| --- | --- |
| `_pages/` | About / CV / Projects などの固定ページ |
| `_posts/` | ブログ記事 |
| `_news/` | News（お知らせ）項目 |
| `_projects/` | 研究プロジェクトのカード |
| `_bibliography/` | 業績（BibTeX） |
| `_data/` | プロフィール・各種設定データ |
| `assets/` | 画像・CSS・JS などのアセット |
| `_config.yml` | サイト全体の設定 |

## ローカルでの確認方法

### Docker を使う場合（推奨）

Ruby を入れずに、al-folio 公式のビルド済みイメージ（`amirpourmand/al-folio:latest`）でそのまま確認できます。
[docker-compose.yml](docker-compose.yml) がこのイメージを使う設定になっています。

```bash
docker compose up
```

起動後、ブラウザで <http://localhost:8080/web/> を開きます（ポートは **8080**、`baseurl` の `/web/` を忘れずに）。
ファイルを編集すると自動で再ビルドされます。終了は `Ctrl + C`、コンテナを片付けるなら:

```bash
docker compose down
```

> イメージは**初回の `docker compose up` のときに一度だけダウンロード**され、以降はローカルにキャッシュされたものが使われます（毎回ダウンロードは不要）。
> もし手元にイメージが無いとき・最新化したいときだけ、明示的に取得できます:
>
> ```bash
> docker pull amirpourmand/al-folio:latest
> ```
>
> 取得済みか確認: `docker images amirpourmand/al-folio`

### Ruby を直接使う場合

Ruby と Bundler が必要です。

```bash
bundle install
bundle exec jekyll serve
```

起動後、ブラウザで <http://localhost:4000/web/> を開きます。

## クレジット

本サイトは [al-folio](https://github.com/alshedivat/al-folio) テーマ（MIT License）をベースにしています。
テーマ本来の README は [README.al-folio.md](README.al-folio.md) に保存してあります。

## ライセンス

サイトのコンテンツ（文章・画像など）の著作権は永井陽斗に帰属します。
テーマ部分は [MIT License](LICENSE) に従います。

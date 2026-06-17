---
layout: post
title: 修論・卒論カウントダウンタイマーを作って GitHub Pages で公開
date: 2026-06-17 10:00:00+0900
description: 提出締切までの残り時間を表示するエヴァ風タイマーを作り、Python 不要のブラウザ完結アプリとして GitHub Pages で公開しました。
tags: 開発
categories: side-project
thumbnail: assets/img/thesis_timer.png
---

修論・卒論の提出締切まであと何時間かを表示する、エヴァ風のカウントダウンタイマーを作りました。

🔗 公開ページ: <https://n-haru0524.github.io/thesis_timer/>
💻 ソースコード: <https://github.com/N-Haru0524/thesis_timer>

{% include figure.liquid loading="eager" path="assets/img/thesis_timer.png" class="img-fluid rounded z-depth-1" %}

## どんなもの

提出締切までの残り時間を、時:分:秒:1/100秒まで表示するタイマーです。
締切が近づくと背景色が `safe → warn → danger` と変化して、否が応でも焦らせてくれます。

- **safe**: 締切まで 7 日（168 時間）以上
- **warn**: 締切まで 7 日以内
- **danger**: 締切まで 3 日（72 時間）以内、または締切超過

修論／卒論の締切を切り替えたり、残り時間表示（REMAIN）と締切の絶対日時表示（ABSOLUTE）を切り替えたりできます。

## Python アプリから Web 完結へ

もともとは Python（pywebview）で動かすデスクトップアプリとして作っていました。
ただ「実行に Python 環境が必要」というのが地味に面倒で、開くたびに準備がいるのが難点でした。

そこで、締切までの残り時間と状態（safe/warn/danger）を計算していた Python のロジックを
すべて JavaScript に移植し、**ブラウザだけで完結する静的サイト**に作り替えました。
これで URL を開くだけで動くようになり、スマホからでも見られます。

締切やしきい値は JavaScript の先頭にまとめてあり、ここを書き換えて `git push` するだけで更新できます。

```js
const DEADLINES = {
  bachelor: "2027-02-10T12:00:00+09:00", // 卒論
  master: "2027-02-02T15:00:00+09:00", // 修論
};
const WARN_HOURS = 168.0; // 7日: safe → warn
const DANGER_HOURS = 72.0; // 3日: warn → danger
```

## デプロイ

公開は GitHub Pages + GitHub Actions です。
`main` ブランチに push すると、ワークフローが自動でサイトを更新してくれます。
サーバーも不要で、運用コストはゼロ。手軽さの面でも Web 完結にしてよかったです。

今年こそ締切に追われすぎないよう、このタイマーを横目に進めていきます。

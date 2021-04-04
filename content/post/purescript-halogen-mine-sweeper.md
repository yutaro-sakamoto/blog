---
title: Purescript + Halogenでマインスイーパを作ってみた.
date: 2021-04-04T17:54:58+09:00
draft: false
---

とりあえず動くものができてよかった.

[こちらから遊べます](/mine-sweeper/index.html)

[ソースコードはこちら](https://github.com/yutaro-sakamoto/sample-purescript-halogen-mine-sweeper)

開発過程でたくさんコンパイルエラーを出しましたが,コンパイルさえ通ってしまえば実行時エラーが起きることはほぼなかったです.
Type-Safeの恩恵を実感できました.

以下,反省点.

* Halogen特有の機能はほとんど使用していない.多分Elmと大差ない.
* ソースコードにコメントを記述していない.
* 2次元Arrayを縦横無尽に駆け回る処理をきれいに記述できなかった.なにか良い方法がないかな?
* UIをもう少しきれいにしたかった.

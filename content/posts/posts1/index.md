---
title: "Kria KR260とEdge Impluseを使ってBasys3を認識させる"
date: 2023-02-28
categories: ["Kria KR260", "edge impulse"]
tags: ["markdown"]
---



[このサイト](https://www.hackster.io/whitney-knitter/edge-impulse-on-kria-kr260-ed12bc)
を参考にして、自前のBasys3を学習させて、認識できるようにやってみた。

必要なもの、こと
- Kria KR260 x 1
- USBカメラ(ロジクールBRIO) x 1
- Edge Impluseのアカウント登録
- MicroSDカード x 1

AMDのサイトに行って、Kria KR260用のubuntuをダウンロードしてMicroSDカードに焼く。
https://www.xilinx.com/products/som/kria/kr260-robotics-starter-kit/kr260-getting-started/booting-your-starter-kit.html

Kria KR260にMicroSDカードをさして、起動。

edge impluse用のパッケージをインストール。

edge impluseのサイトにログインして、training、test用の画像を撮影。
　全体で、41枚撮影して、training用に37枚、test用に4枚使いました。
![basys3_training](basys3_training.png)


撮影した画像にlabelingしていきます。今回は、Basys３を認識させたいので
Basys3の写っている範囲を指定しています。
![basys3_label](basys3_label.png)

精度を確認したところ、50％ぐらいでした。今回はとりあえず動かしたかったので
追加でtraining画像を増やしたりしませんでした。
![basys3_test](basys3_test.png)

Kria KR260でedge impulseを実行した結果以下の図のように上手いことbasys3に
カメラを向けると認識してくれます。
![basys3](basys3_photo.png)

今回は精度が50%でしたが、もっと良くするためにいろんな角度の画像を撮影した方がいいです。
（今回はほぼ正面の画像のみ）
# モンテカルロ法の演習

# 進め方
## はじめてのとき
* [GitHub](https://github.com/)のアカウントを作成してください
* [Travis CI](https://travis-ci.org/) のアカウントを作成してください
* GitHubのアカウントを[こちらのフォーム](https://goo.gl/forms/anAdoxqPKVt8sJGZ2)から教えてください。
## 毎回の進め方
* このリポジトリをforkしてください
* Travis CI を設定して、自動ビルドが通るようにしてください
   * Travis CI のGitHubアカウントでの登録とforkしたリポジトリをTravisCI側で許可する
   * 参考サイト：[Travis CI入門 Travis CIとGitHubでCIを実現する方法(Change the World!)](http://changesworlds.com/2014/09/introduction-to-travis-ci-and-github-001/)
* forkしたリポジトリの README.md ファイルの「t-kougei-game-comp」の部分を自分のGitHubアカウント名に差し替えてください(2箇所)
* 問題を解いて、テストを通るようにしてください。
* fork 元の master ブランチにプルリクエストを投げてください

# テスト結果

[![Build Status](https://travis-ci.org/t-kougei-game-comp/rand.svg?branch=master)](https://travis-ci.org/t-kougei-game-comp/rand)

# 今回の問題

モンテカルロ法の勉強です。

乱数を用いてπの計算をします。

input?.txt ファイルを標準入力として読み込んで、標準出力の結果を output?.txt ファイルと一致するか比較するテストをします。

main.c ファイルだけを書き換えて下さい。

## 入力される値
入力は以下のフォーマットで与えられます。
~~~
n
~~~
nは正の数字です。

## 期待する出力

-1.0から+1.0までの2個の乱数x,yを生成し、その変数を2次元の座標(x,y)と見なした点と原点との距離を計算します。
距離が1.0以下となる点の割合を数え、その割合を4倍した数を表示してください。
入力した点の数だけ点を生成してください。

最後は改行し、余計な文字、空行を含んではいけません。

## 条件
すべてのテストケースで数字は以下の条件を満たします。
* 0 <= n <= 2147483647(0x7fffffff)

乱数の生成は、合同線形法のC+11のminstd_randの方法で行い、seedは0で始めること。
生成した乱数をIEEE 754 の単精度浮動小数点数へビット演算で変換して[1.0,2.0]の浮動小数点を求めたあと、スケーリングで、[-1.0,+1.0]に変換する事。

## 入力例1
~~~
1
~~~

## 出力例1
~~~
1.00000
~~~

## 入力例2
~~~
1
6
10
~~~

## 出力例1
~~~
1
1
4
6
6
2
4
3
2
5
~~~

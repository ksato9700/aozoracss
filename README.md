# aozoracss

[青空文庫](http://www.aozora.gr.jp/)のXHTML形式の文章ファイルを表示するためのスタイルシート(CSS)を作成するためのプロジェクトです。

## プロジェクトの目的

現状のCSSファイルは[ここ](http://www.aozora.gr.jp/cards/aozora.css)にあり、特に問題なく利用されてきましたが、暫く更新がされておらず、モバイルデバイスでの表示に難があるなどの問題がちらほら見え始めてきました。CSSの新たな機能に対応したブラウザも増えてきているので、今後の拡張や新たな要求を満たす為の土台として、スタイルシートを新たに作成し、維持拡張していくのがこのプロジェクトの目的になります。

## 設計方針

新たにスタイルシートを作成するに当たり、次を設計の方針とします。
 - 過去互換性は確保し、既存のXHTMLファイルが問題なく表示できるようにする。
 - 保守性向上のために、CSSプリプロセッサを導入する。
 - [レスポンシブウェブデザイン](https://ja.wikipedia.org/wiki/%E3%83%AC%E3%82%B9%E3%83%9D%E3%83%B3%E3%82%B7%E3%83%96%E3%82%A6%E3%82%A7%E3%83%96%E3%83%87%E3%82%B6%E3%82%A4%E3%83%B3)を導入する
 - CSS3などの新たな仕様を積極的に利用する。
 - 縦書き表示の為の追加スタイルシートを用意する
 
## 利用方法
### sassのインストール
[ここ](http://sass-lang.com/install)を参照していただくのが確実ですが、コマンドラインで入れるのであれば
```
$ gem install sass
```
あるいは
```
$ sudo gem install sass
```
でいけるはずです。

### aozora.cssの生成
Sassがインストール済みであれば、
```
$ sass aozora.scss aozora.css
```
で生成されます。

## テスト

```
$ ruby -rwebrick -e 'WEBrick::HTTPServer.new(:DocumentRoot => "./", :Port => 8000).start'
```
としてローカルホストにHTTPサーバを立てます。そしてWebブラウザで http://localhost:8000/sample/senten_sample.html にアクセスすれば見られると思います。

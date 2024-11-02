## フォームを作成しよう
フォームを作成する前に以下の三つの手順を行います。

① Formクラスを作成する


② コントローラーを変更する


③ ビューを作成する

## ①Formクラスを作成しよう
最初にFormクラスを作成します。Formクラスとは、フォームに入力されたデータを格納するためのクラスです。


railsでは、paramsというハッシュによって自動で保存ができました。
それに代わるものとして、javaのFormクラスは自前で作成します。


最初に、以下の内容で新規ファイルを作成しましょう。

保存場所：src/main/java/in.techcamp.firstapp


種類：クラス


名称：PostForm

[![Image from Gyazo](https://i.gyazo.com/d3223be686bd849b0328ca9081856a58.png)](https://gyazo.com/d3223be686bd849b0328ca9081856a58)




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



このコードはPostEntityと似ていますが、@AllArgsConstructorのアノテーションを使用していません。

Lombokによってセッター・ゲッターのみを追加しているので、このクラスには以下が含まれることになります。

- memoという名称のString型の変数
- 変数memoのセッター
- 変数memoのゲッター

ここまでの作業でFormクラスの作成は完了です。

続いてコントローラーを変更しましょう。
PostControllerを以下のように変更しましょう。



##  ②コントローラーを変更しよう
いま作成したFormクラスをビューに渡すことによって、フォームの入力内容とFormクラスを関連づけます。
src/main/java/in.techcamp.firstapp/PostController.java
いま変更したコードの、以下の箇所に注目しましょう。


PostControllerを変更しよう

[![Image from Gyazo](https://i.gyazo.com/eb0825b3048a4c02df7d0e7e568d0fff.png)](https://gyazo.com/eb0825b3048a4c02df7d0e7e568d0fff)

いま変更したコードの、以下の箇所に注目しましょう。

` public String showPostForm(@ModelAttribute("postForm") PostForm form`

ここで@ModelAttributeというアノテーションを使用しています。このアノテーションを使用すると、任意のデータをModel型のオブジェクト内に格納することができます。

Spring Bootでは、このModel型のオブジェクトは特別な意味を持っており、データの一時保管場所のように活用することができます。




`@ModelAttribute("呼び出すときの名称") 保存したい変数のデータ型　保存したい変数`


コントローラーでこの保管場所にデータを保管しておき、それをビューで呼び出すという使い方になります。

具体的な使い方は、以下のようになっています。
`@ModelAttribute("呼び出すときの名称") 保存したい変数のデータ型　保存したい変数`

今回は、以下のように使用しています。

`@ModelAttribute("postForm") PostForm form`

このコードによって、PostForm型の変数formを登録し、後で「postForm」という名称で呼び出すことができます。


##  ③ビューを作成しよう

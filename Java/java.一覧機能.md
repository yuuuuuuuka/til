# 一覧表示機能を実装

Javaでデータベースを利用することは少し難しいため、以下の流れで実装を行なっていきます。


① データベースは使用せず、コントローラー内で作成したリストをビューで表示できるようにする


② データベースと連携し、テーブル内のデータをビューで一覧表示できるようにする


FirstAppでは、以下のようにidカラムとmemoカラムのみを扱うシンプルなテーブルを作成します。
>id: 投稿ごとにつけるid

>memo：	投稿されたテキスト


# 一覧表示機能の実装


### 一覧表示用のビューを作成する
##### ビューファイルの編集・作成
[![Image from Gyazo](https://i.gyazo.com/73e8ea956f1580c3f8a9725dedc31cec.png)](https://gyazo.com/73e8ea956f1580c3f8a9725dedc31cec)

[![Image from Gyazo](https://i.gyazo.com/516ee1be545302a349aa7064af99c63f.png)](https://gyazo.com/516ee1be545302a349aa7064af99c63f)


一覧表示を行うためのメソッドを、「showList」という名称で追加しています。



また、**@GetMapping**とアノテーションの記述を行なっていますが、これは **@GetMapping("/")** と書くのと同じ意味です。ルートパス（/）を指定する場合の **("/")は省略可能** です。

以下のように　ルートパスにアクセスできていたら成功です！

[![Image from Gyazo](https://i.gyazo.com/38d72e2316c9b676bbe7d58496edd081.png)](https://gyazo.com/38d72e2316c9b676bbe7d58496edd081)

### エンティティを作成する



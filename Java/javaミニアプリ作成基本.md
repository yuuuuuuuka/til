## アプリを作成する大まかな作業手順  
1.　アプリの雛形を作成する  
2.　ルーティング・コントローラーの作成を行う  
3.　ビューを作成する   

  
## 使用するツールについて  
**Java:** プログラミング言語　

**SpringBoot：**　Javaのフレームワーク

**IntelliJ IDEA:** 統合開発環境です。プログラミングに必要なさまざまな**ツールや機能が一つにまとまっていて**、環境設定が少なくて済みます。 (railsでいうVScode)



(※統合開発環境とは、ソースコードの記述、ビルド、テスト、デバッグといった開発作業全般を支援し、一つのソフトウェア内で完結させられるように設計された開発ツールのこと。)

## アプリの雛形を作成しよう　
### 1.ファイル作成  
1.ファイルを作成するために以下のURLにアクセスする（https://start.spring.io/）　

2.Prijectでビルドツールの選択・SpringBootのバージョン選択・ProjecyMetadataの設定を行う  
3.ライブラリの設定(Dependencies」の欄にある、「ADD DEPENDENCIES」のボタンをクリック。)　
メニューが表示されるので、検索ワードとして、「web」と入力　→「Spring Web」をクリック　　

#### Spring Webとは？　
Spring Frameworkが提供するWebアプリケーション開発のためのモジュールです。

#### なぜ　SpringWebが必要なのか？
以下の機能を使うことができるから
- Webアプリケーションの基盤: Spring Webは、Spring BootでWebアプリケーションを開発するための基盤となるモジュールです
- HTTPリクエスト処理: Webサーバーとクライアント間のHTTPリクエストを処理するための機能を提供します。
- REST API開発: RESTfulなWebサービスを簡単に開発するための機能を提供します。
- Web MVC: Model-View-Controller (MVC)パターンに基づいたWebアプリケーション開発をサポートします。

### 2.プロジェクトファイルをダウンロードする   
入力内容が正しいか確認できたら「GENERATE」ボタンをクリック→ファイルがダウンロードされる。 
### 3.　ダウンロードしたファイルをIntelliJで読み込む  

1.ダウンロードしたファイルを専用のディレクトリに移動 
##### 2.IntelliJを起動からプロジェクトを実行まで
起動したら上部メニューバーから「ファイル」-「開く」を選択します   

1)build.gradle→「プロジェクトとして開く」→、「プロジェクトを信頼」→ ビルド　（ターミナルに完了が出たら成功）　 

2)firstapp」「src」「main」「java」「in.techcamp.firstapp」フォルダにある「FirstAppApplication」を右クリック
⇨'OOAppliica..main()'の実行をクリックしましょう。　
[![Image from Gyazo](https://i.gyazo.com/b77542ea1334e65327b6077a1d9bb1e7.png)](https://gyazo.com/b77542ea1334e65327b6077a1d9bb1e7)
🙆‍♀️タスクを実行中とターミナルに表示されれば実行完了！
[![Image from Gyazo](https://i.gyazo.com/4f5a8d7b5d7c79d04921467290dbaad2.png)](https://gyazo.com/4f5a8d7b5d7c79d04921467290dbaad2)
Chromeで、以下のURLにアクセスして確認してみましょう！

localhost:8080/

以下のような表示になっていれば成功です！
[![Image from Gyazo](https://i.gyazo.com/a95b5187bed393d159d556dd69f9d353.png)](https://gyazo.com/a95b5187bed393d159d556dd69f9d353)

### 🎊Javaアプリの雛形を作成し、実行することができました🎊


## IntelliJの画面の見方
ここから機能を追加し、FirstAppを作成していきます。　
まず初めに、IntelliJの画面の見方を理解しておきましょう。

[![Image from Gyazo](https://i.gyazo.com/bd72ecbb842df9bbddf8620985cc0726.png)](https://gyazo.com/bd72ecbb842df9bbddf8620985cc0726)
もっとも使われるのが、mainフォルダ内の、以下のフォルダは非常によく使用するものです。 

##### java:                    javaコードを格納しておく場所です。 
##### resources:  ビューのためのHTML・CSSを格納します。
##### build.gradle: 使用するライブラリの追加や編集ができる（RailsのGemfile） 

## アプリの実行・停止方法

プロジェクトを始めて実行するときは、「FirstAppApplication」ファイルを右クリックしていましたが、2回目以降にアプリを実行する際は、【実行】ボタン▶️をクリックします。 

実行するとアイコンが↪️のようなマークに変化します。この意味は、【再実行】と言う意味です。 
**アプリを実行している状態でコードを変更した場合は、この「再実行」ボタンをクリックする必要があります。**  
アプリを停止する際は、以下の⏹️「停止ボタン」をクリックしましょう。



# コントローラーを作成
①コードを記述するためのクラスファイルを新規作します。

[![Image from Gyazo](https://i.gyazo.com/7f8ffc928e7b6ecbe38eac72ca228733.png)](https://gyazo.com/7f8ffc928e7b6ecbe38eac72ca228733)
[![Image from Gyazo](https://i.gyazo.com/b94071f6f9dafc2ac2a0070dafd945b2.png)](https://gyazo.com/b94071f6f9dafc2ac2a0070dafd945b2)
[![Image from Gyazo](https://i.gyazo.com/d6b8bc494c0b5464da3648341b9d24fd.png)](https://gyazo.com/d6b8bc494c0b5464da3648341b9d24fd)

⚠️railsでコントローラの命名を行う際は、**PostsController**のように複数形にする規則がありましたが、Javaにはその規則はありません。

‼️javaはコードの記述量が多くなりがちなので、IntelliJの補完機能等をうまく利用することが重要‼️  
「@Controller」を入力している途中で、以下のように**補完用のウィンドウが開きます。**
[![Image from Gyazo](https://i.gyazo.com/88797e735b1c8a967b5f2d0f52030392.png)](https://gyazo.com/88797e735b1c8a967b5f2d0f52030392)



するとコード入力が補完され、以下の状態になります。 


[![Image from Gyazo](https://i.gyazo.com/20b9dacad20e77dd2bd9044955c8c16a.png)](https://gyazo.com/20b9dacad20e77dd2bd9044955c8c16a)

2つの行が追加されてました。 
① 3行目にimport文が追加される 

② 5行目の@Controllerという文字が補完される 

このように、入力しようとしていた「@Controller」だけで、IntelliJの補完機能により自動でインポート分が入力される

[![Image from Gyazo](https://i.gyazo.com/1c67a96700f1ba24b063921ff6d81c41.png)](https://gyazo.com/1c67a96700f1ba24b063921ff6d81c41)
[![Image from Gyazo](https://i.gyazo.com/7698fcbfc37a93b058b52d0070d6d095.png)](https://gyazo.com/7698fcbfc37a93b058b52d0070d6d095)

上記のように「/hello」というパスが指定されると「Hello World!」と表示するアプリができました


# アノテーション（＠）とは
アノテーションとは、クラスやメソッドに特別な意味を持たせるための機能です。　 
ソースコードに注釈を付けるための仕組みです。

例えるなら、文章に付箋を貼って**補足説明をするようなものです。**
この**付箋に当たるのがアノテーション**で、コードの特定の部分に付加することで、コンパイラや開発ツールに特別な指示を与えることができます。 

## 💡アノテーションの役割 
### 1.クラス、メソッド、変数などに追加情報を付与します。

(例: @Override：メソッドが親クラスのメソッドをオーバーライドしていることを示す)

  **【railsで例えるなら　モデルの属性`:validates :name, presence: true/belongs_to :user`】**
  
  - モデルの属性に対して制約や関連付けを設定しており、Javaのアノテーションがクラスやメソッドにメタデータを付与するのと同様に、モデルの振る舞いを定義しています。

### 2. コンパイラに対して、コードのチェックや生成を行うように指示します。


(例: @SuppressWarnings：特定の警告を抑制する)
### 3. フレームワークがアノテーションを読み取って、特定の処理を実行します。
 (例: Spring Frameworkの@Autowired：依存性の注入を行う)
 
【rails で例えるならコントローラーのアクション：  `before_action :authenticate_user!
skip_before_action :verify_authenticity_token`】
  
- これらは、コントローラーのアクション実行の前後に行う処理を定義しており、Javaのアノテーションがメソッドに実行時の振る舞いを付与するのと似ています


  ## 具体的な使い方
  [![Image from Gyazo](https://i.gyazo.com/ac5e2ec36ecdea200c3f993075f9c8a9.png)](https://gyazo.com/ac5e2ec36ecdea200c3f993075f9c8a9)

  このコードで３つの＠があります。
  - @Controller
  - @GetMapping("/hello")
  - @ResponseBody
「PostControllerクラス」の直前には「@Controller」が付けられ、showHello()メソッドの前に「@GetMapping」と「@ResponseBody」が付けられています。

それぞれどんな意味を持つのか順番に説明していきます！

### それぞれのどんな意味？
## @Controller:
そのクラスがコントローラーであることをSpringに伝えるためのアノテーションです。


- Springでは、クラス定義の直前に「@Controller」と記述することで、クラスがコントローラーとして扱われるようになります。

- Spring Bootのアプリ実行時にコンポーネントスキャンという処理が行われますが、スキャン中にアノテーションを発見すると、それが付けられたクラスに対して必要な事前準備が行われる仕組みです。

>📚コンポーネントスキャン：特定のアノテーションが付与されたクラスを自動的に検出し、DIコンテナに登録する仕組み

>📚DIコンテナ：オブジェクトの生成や管理を行うためのコンテナで、コンポーネントスキャンによって登録されたクラスは、DIコンテナによって管理される

## @GetMapping:
ブラウザで入力されたURLと、実行されるメソッドを紐づけるためのアノテーションです。
- @Mappingは、Railsのルーティングと同様の機能です。


## @ResponseBody:
- ブラウザからのリクエストに対して、直接HTMLを返す際に利用するアノテーションです。


また、アノテーションを利用するためには、適切なインポートが必要です。

**インポート:** Javaファイルの先頭に配置し、利用するアノテーションをに指定することで、アノテーションの機能を利用できます。
[![Image from Gyazo](https://i.gyazo.com/ca719b99f7b3ef5fec6ca6ddc8c2433e.png)](https://gyazo.com/ca719b99f7b3ef5fec6ca6ddc8c2433e)





## アノテーション以外のコントローラーの記述方法を理解しよう
 [![Image from Gyazo](https://i.gyazo.com/5c7358c586b68eae914b22f577b385b8.png)](https://gyazo.com/5c7358c586b68eae914b22f577b385b8)
#### PostContorllerクラスは、コントローラーとして扱われる

  
このコントローラー内で、「(アプリのルートパス)/hello」とURLが入力されたら「showHello()メソッド」が実行されるよう設定されている
#### showHello()メソッドの中身について確認しましょう。

 `showHello()`の前に、「String」と記述されているので、これは返り値が「文字列」のメソッドであることが分かります。

 つまり、このshowHello()メソッドは、実行すると`<h1>Hello World!</h1>`という文字列を返すメソッドです。この文字列がHTMLとして解釈され、ブラウザに表示される仕組みです。

 しかし、現状のビューの表示方法は一般的ではありません。

Railsでは、ERBというテンプレートエンジンを使用して、コントローラーとビューのコードを分離して管理しやすくしたと同様に、Spring BootにはThymeleaf（タイムリーフ）というライブラリを使っていきます。

## Thymeleafの導入から実際に使用してみよう！

#### 導入方法
1.ルートディレクトリにある「build.gradle」ファイル内のdependenciesブロックに、以下のように追記しましょう。（RailsのGemfileに似た役割を持つものです。）

🔴の行を追加しました。その後二枚目のマークを押すと実行され準備完了です。
[![Image from Gyazo](https://i.gyazo.com/630a138bf6f7972a8c902c6117a5003f.png)](https://gyazo.com/630a138bf6f7972a8c902c6117a5003f)
[![Image from Gyazo](https://i.gyazo.com/97a283c1b4d6bf3a3b41ca66dfa9c99a.png)](https://gyazo.com/97a283c1b4d6bf3a3b41ca66dfa9c99a)

続いて実際にThymeleafを使用していため2つの作業を行なっていきます。

### ①表示させるためのHTMLを作成する

「firstapp」「src」「main」「resources」フォルダにある「templates」フォルダを右クリックします。

メニューの中から、「新規」「HTMLファイル」を選択して「hello.html」というファイルを作ります。


[![Image from Gyazo](https://i.gyazo.com/3c53811cea00e063f9b81bf4a06b79d3.gif)](https://gyazo.com/3c53811cea00e063f9b81bf4a06b79d3)


[![Image from Gyazo](https://i.gyazo.com/b61eef740859195b26ae69e204858aec.png)](https://gyazo.com/b61eef740859195b26ae69e204858aec)


### ②コントローラーを変更
### Thymeleafで変数を使おう
コントローラーからビューに変数を渡して表示させる方法について学習していきましょう。

4行目と16・17行目を記述しました。
[![Image from Gyazo](https://i.gyazo.com/99e64fae5e6de1197e0dce0c8336a1c3.png)](https://gyazo.com/99e64fae5e6de1197e0dce0c8336a1c3)


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



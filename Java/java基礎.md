# 変数の種類

変数の扱う種類は **『動的型付け言語』**　と **『静的型付け言語』**　の２種類がある
上記の説明の前にまず、データ型について説明します。

## データ型とは？
データ型とは変数に格納するデータの種類のことを指します。（stringやintなど）
#### なぜ必要？
データ型があることで、コンピュータのリソースを効率よく使うことができる。
#### 具体的には
- データ型を適切に選ぶことで、不要なメモリを消費することを防ぎ、より多くのデータを扱うことができるようになる
- 異なるデータ型の値を混在させて計算すると、予期せぬ結果になったり、プログラムが異常終了したりすることがある
- 異なるデータ型の値を混在させて計算すると、予期せぬ結果になったり、プログラムが異常終了したりすることがある。
  
  
## 動的型付け言語(ruby)と静的型付け言語（java）の違い
### 動的型付け言語
``` a = 1
puts(a * 2)
# 2と出力される　数値演算で処理

a = "alphabet"
puts(a * 2)
# alphabetalphabetと出力される　文字列で処理
```
結論：どのような値が代入されたかによって、変数のデータ型が **柔軟**に変更され、そのデータ型に基づいて処理が行われている。


### 静的型動機づけ
```class Main {
  public static void main(String[] args) {
    int radius; // 変数の前に形を宣言
    radius = 5;
    System.out.println(radius * radius * 3.14);
  }
}
```
- 変数のデータ型を最初に決定したら変更できない。  
- 最初に「整数」として宣言した変数に、「文字列」を代入しようとするとエラーになる。


#### 型推論　
型推論とは、値の種類によってデータ型が推論され、推論されたデータ型で宣言が行われる。
```var 変数名 = 値```
つまり、コードを省略することができる

```class Main {
  public static void main(String[] args) {
    var radius = 5;
    System.out.println(radius * radius * 3.14);
  }
}
```

## javaの配列
**格納する要素の数を最初に決める必要があり、かつ後で要素数を変更することができない**  

要素を増やす場合、**ArrayLis**tというリストの一種を使用する必要がある。
## ArrayListとは
- 要素の数を変更できる配列
- 要素を動的に追加・削除できる
- javaの標準ライブラリの一部のため、直接使うにはインポートしてプログラムに存在を知らせる必要がある


```
import java.util.ArrayList; //インポートをしてArrayListを知らせる

class Main {
  public static void main(String[] args) {
    ArrayList<Integer> scores = new ArrayList<Integer>();

    scores.add(1);
    scores.add(5);

    System.out.println(scores.get(0));　// 出力は　1
    System.out.println(scores.get(1));　// 出力は　5
   
  }
}
```

## ArrayListを使った配列の使い方
① ライブラリをインポートする  


ArrayListを使用する際は、ライブラリのインポートが必要  

`import java.util.ArrayList;`  

② ArrayListの宣言を行う  

`ArrayList<Integer> scores = new ArrayList<Integer>();`  

- 整数（Integer）を格納するArrayListを「scores」という名称で宣言
- ArrayListの要素を作成。　　` new ArrayList<>();`←省略も可能。
  
③ ArrayListに値を代入する

addメソッドで1を追加  

`scores.add(1);`  

④ ArrayListから要素を取り出す  

get()で要素を取り出します。  

`scores.get(0)`  


# 条件分岐
```
class Main {
  public static void main(String[] args) {
    int value = 3;

    if (value > 0){
      System.out.println("値は正です"); 
    }else if (value < 0){
      System.out.println("値は負です"); 
    }else {
      System.out.println("値は0です"); 
    }
  }
}
```
if文の定義はrubyとよく似ている。 
Rubyでの記述方法と異なるのは以下の点です。

・条件式を（）で囲む
・行いたい処理を{}で囲む

# 繰り返し処理 （拡張for文）
```
class Main {
  public static void main(String[] args) {
    int[] scores = {1, 5, 10};

    for(int score : scores) {
      System.out.println(score);  //1 5 10 が出力される
    }
  }
}
```

拡張for文のコードの定義は以下になります。
```
for ( 要素を格納する変数宣言  :  配列あるいはArrayListの変数名) {
  取り出した要素を使用して行う処理
}
```

上記のコードを参照すると  

① 配列から要素を1つ取り出す（ArrayListの場合も同様)


② 取り出した要素を変数に代入する  

③ {}内の処理を行う  

④ 配列、あるいはArrayListの要素数分だけ処理を繰り返す  






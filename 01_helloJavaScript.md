# Hello JavaScript


## プログラムの書き方

### はじめの一歩

 1. 新しく空のファイル「sample.html」を作成します。
 1. テキストエディターで「sample.html」を開き、以下のプログラムを書きます。

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
</head>
<body></body>
<script>
// プログラムはここから


// ここまでの間に書きます。
</script>
</html>
```

ブラウザーで実行する場合、javascriptはHTML中の``<script>``タグで囲む、もしくはリソース（``src``）として指定されたファイルの中で実行されます。

 + リソースとして指定する場合の例(hoge.jsファイルにプログラムを書く)

```javascript
<script src="hoge.js"></script>
```

今回は``<script>``タグで囲んだ中でプログラムを書いていきます。

## プログラム書いて結果を表示させる。

まず、簡単なプログラムとして、「hello JavaScript」を様々な方法で表示してみましょう。

### ブラウザに表示してみる。

ブラウザに表示させる方法は色々ありますが、手軽く表示させる方法として、以下を紹介します。

以下の内容を「プログラムはここから」の下に書いたのち、「sample.html」をブラウザで実行してみてください。

```javascript


document.body.innerText = "Hello JavaScript";


```

ブラウザに「Hello JavaScript」と表示されていれば成功です。

続けて、「Hello JavaScript」の内容を自分なりに変えてみて、ブラウザのリロード（F5キー、もしくはブラウザの更新ボタン）を行って見てください。

書き換えた内容で、ブラウザ上の表示が変われば成功です。


### アラートを表示してみる。

これはalertダイアログというポップアップで表示させる方法です。


```javascript


alert("hello JavaScript");

```

### コンソールログに表示してみる。

```javascript


console.log("Hello JavaScript");

// カンマ区切りで渡すことも可能です。
console.log("Hello", "JavaScript");

```

コンソールの表示方法はブラウザによって様々です。

| ブラウザ | ショートカットキー |
|:---|:---|
| FireFox | ``Ctrl`` + ``Shift`` + ``i`` |
| Chorme | ``Ctrl`` + ``Shift`` + ``i`` |
| IE | ``F12`` |


### 入力してみる

入力処理を作ってみましょう。

以下のサンプルは、ダイアログを表示して、入力した結果をログに書き出すと言う処理です。

今回は、入力/操作を行いたい場合は以下の機能を使っていきます。

```javascript

console.log( window.prompt("名前を入れてください。") );

```

## プログラムの流れ

javascriptは手続き型の言語です、プログラムは基本的に上から下に向かい、1行づつ処理されていきます。

```javascript


console.log("こんにちは");
console.log("私は");
console.log("JavaScript");
console.log("はじめました。");

```

## コメントの書き方。

プログラムにはメモや後で見た人がわかりやすいよう、コメントを残すことが出来ます。

コメントはプログラムの動作に影響を与えません。

動かしたくないけれども、せっかく書いたものを消したく無い場合等にも使えます。

#### 1行コメント

```javascript


// これは「hello world」とコンソールに出力します。
console.log("hello world");


```

#### 複数行に渡るコメントを書く場合。

```javascript 


/*
これは
hello world
とコンソールに出力します。
*/
console.log("hello world");

```




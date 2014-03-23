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

ここにプログラムを書きます。

</script>
</html>
```

## プログラム書いて結果を表示させる。

まず、簡単なプログラムとして、「hello JavaScript」を様々な方法で表示してみましょう。

### ブラウザに表示してみる。

ブラウザに表示させる方法は色々ありますが、手軽く表示させる方法として、以下を紹介します。

```javascript


document.body.innerText = "Hello JavaScript";

```

### アラートを表示してみる。

これはalertダイアログというポップアップで表示させる方法です。


```javascript


alert("hello JavaScript");

```

### コンソールログに表示してみる。

```javascript


console.log("Hello JavaScript");

```

コンソールの表示方法はブラウザによって様々です。

| ブラウザ | ショートカットキー |
|:---|:---|
| FireFox | ``Ctrl`` + ``Shift`` + ``i`` |
| Chorme | ``Ctrl`` + ``Shift`` + ``i`` |
| IE | ``F12`` |


## プログラムの流れ型

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




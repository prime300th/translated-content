---
title: JavaScript の基本
slug: Learn/Getting_started_with_the_web/JavaScript_basics
---
{{LearnSidebar}}{{PreviousMenuNext("Learn/Getting_started_with_the_web/CSS_basics", "Learn/Getting_started_with_the_web/Publishing_your_website", "Learn/Getting_started_with_the_web")}}

JavaScript はウェブサイトにインタラクティブ機能 (ゲーム、ボタンが押されたときやデータがフォームに入力されたときの反応、動的なスタイルの変更、アニメーションなど) を追加するプログラミング言語です。この記事は、このエキサイティングな言語を始めるのに役立ち、可能性についてのアイディアを提供します。

## JavaScript とは何か

{{Glossary("JavaScript")}} (略して "JS") は成熟した{{Glossary("Dynamic_programming_language", "動的プログラミング言語")}}であり、{{Glossary("HTML")}} 文書に適用すると、ウェブサイトに動的な対話操作を提供できます。Mozilla プロジェクト、Mozilla Foundation、Mozilla Corporation の共同設立者である Brendan Eich によって考案されました。

JavaScript は汎用性が高く、初心者にもやさしいものです。経験を積めば、ゲーム、 2D や 3D のアニメーション、包括的なデータベース駆動型のアプリなどが作れるようになります。

JavaScript は比較的コンパクトですが、一方でとても柔軟性があります。開発者は JavaScript 言語のコアをベースに多種多様なツールを作成し、最小限の労力で膨大な様々な機能を利用できるようにしました。例えば以下のようなものがあります。

- ブラウザーのアプリケーションプログラミングインターフェイス ({{Glossary("API")}})。ウェブブラウザーに組み込まれた API により、動的な HTML の作成、 CSS スタイルの設定、ユーザーのウェブカメラからの動画ストリームの収集や操作、3D グラフィックやオーディオサンプルの生成などの機能を提供する、ウェブブラウザーに組み込まれた API。
- 開発者が Twitter や Facebook のような他のコンテンツプロバイダーのサイトから機能を組み込むことを可能にする、サードパーティの API。
- すばやくサイトやアプリケーションを構築することができ、 HTML に組み込み可能なサードパーティのフレームワークやライブラリー。

コアの JavaScript 言語が上記のツールとどのように違うのか、その詳細を紹介することは、 JavaScript の軽い入門者向けの書籍であるこの記事の範囲外です。詳細は MDN の [JavaScript 学習エリア](/ja/docs/Learn/JavaScript)や、 MDN の他の部分で詳しく学ぶことができます。

以下では、コア言語のいくつかの側面について紹介します。またブラウザーの API 機能についてもいくつか説明します。楽しみましょう！

## _Hello world!_ の例

JavaScript は、最も人気のある現代のウェブ技術のひとつです。あなたの JavaScript のスキルが上がれば、あなたのウェブサイトのパワーと創造性は新たな次元に入るでしょう。

しかし、JavaScript を使いこなせるようになるのは HTML や CSS よりも少し難しいです。小さなものから始め、小さく確実な手順で作業を続ける必要があるかもしれません。始めるにあたって、_"hello world!"_ を表示する例 ([基本的なプログラミング例の標準](https://en.wikipedia.org/wiki/%22Hello,_World!%22_program)) を作りながら、基本的な JavaScript をページに追加する方法を紹介しましょう。

> **Warning:** **重要**: これまでこのコースに沿って進めてきていない場合は、[このサンプルコードをダウンロードして](https://github.com/mdn/beginner-html-site-styled/archive/gh-pages.zip)作業を進めてください。

1. 最初にテストサイトに行き、 `scripts` という名前の新しいフォルダーを作成してください。それから、 scripts フォルダーの中に `main.js` という新しいファイルを作成して保存してください。
2. `index.html` ファイルの `</body>` 閉じタグの直前に新しい行で、以下の新しい要素を追加してください。

    ```html
    <script src="scripts/main.js"></script>
    ```

3. これは CSS の {{htmlelement("link")}} 要素の時の作業と基本的に同じです。これは JavaScript をページに適用するので、(CSS の時と同じく、ページ上の何に対しても) HTML に影響を与えることができます。
4. `main.js` ファイルに次のコードを追加してください。

    ```js
    const myHeading = document.querySelector('h1');
    myHeading.textContent = 'Hello world!';
    ```

5. 最後に、 HTML と JavaScript を書いたファイルを保存したことを確認し、ブラウザーで `index.html` を読み込んでください。![](hello-world.png)

> **Note:** 上記の説明で {{htmlelement("script")}} 要素を HTML ファイルの末尾付近に置いたのは、**ブラウザーがファイルに現れる順番でコードを読み込むからです**。
>
> JavaScript が先に読み込まれ、まだ読み込まれていない HTML に影響を与えることになると、問題が生じる可能性があります。 JavaScript を HTML ページの下部に配置することは、この依存関係に対応する一つの方法です。その他の方法については、[スクリプトの読み込み戦略](/ja/docs/Learn/JavaScript/First_steps/What_is_JavaScript#script_loading_strategies)をご覧ください。

### 何が起きたのか

JavaScript を使用して、見出しの文字列が _Hello world!_ に変更されました。最初に `{{domxref("Document.querySelector", "querySelector()")}}` と呼ばれる関数を使用して見出しの参照を取得し、 `myHeading` と呼ばれる変数に格納しています。これは CSS のセレクターを使用するのととてもよく似ています。要素に対して何かをしたくなったら、まずその要素を選択する必要があります。

その後、`myHeading` 変数の `{{domxref("Node.textContent", "textContent")}}` プロパティ (見出しの内容を表す) の値を _Hello world!_ に設定します。

> **Note:** 上の例で使用した機能はどちらも[ドキュメントオブジェクトモデル (DOM) API](/ja/docs/Web/API/Document_Object_Model) の一部であり、これを使って文書を操作することができます。

## 言語の短期集中コース

どのように動作するかをよりよく理解できるように、 JavaScript 言語の基本機能のいくつかを説明しましょう。これらの機能はすべてのプログラミング言語に共通しているので、これらの基本をマスターすれば、ほとんど何でもプログラムできるようになります！

> **Warning:** **重要**: この記事では、 JavaScript コンソールにサンプルコードを入力して、何が起こるのかを確認してみます。 JavaScript コンソールの詳細については、 [ブラウザー開発ツールを探る](/ja/docs/Learn/Common_questions/What_are_browser_developer_tools)を参照してください。

### 変数

{{Glossary("Variable", "変数")}} は、値を格納できる入れ物です。まず、 [`var`](/ja/docs/Web/JavaScript/Reference/Statements/var) (説明はややこしいですが、推奨しません) または [`let`](/ja/docs/Web/JavaScript/Reference/Statements/let) というキーワードと、その後に任意の名前を指定することで、変数を宣言します。

```js
let myVariable;
```

> **Note:** 行末のセミコロンは文が終わる場所を示します。単一の行で複数の文を区切る場合には絶対に必要です。しかし、個々の文の末尾に置くことが良い習慣だと信じている人もいます。使用する場面と使用しない場合については他のルールもあります。詳しくは [Your Guide to Semicolons in JavaScript](http://news.codecademy.com/your-guide-to-semicolons-in-javascript/) を参照してください。

> **Note:** 変数にはほとんど何でも名前を付けることができますが、いくらかの制約があります([変数の命名規則についてはこの記事](/ja/docs/Web/JavaScript/Guide/Grammar_and_types#variables)を参照してください)。自信がない場合は、有効かどうか[変数名を調べる](https://mothereff.in/js-variables)ことができます。

> **Note:** JavaScript は大文字と小文字を区別します。`myVariable` は `myvariable` とは異なる変数です。コードで問題が発生している場合は、大文字・小文字をチェックしてください。

> **Note:** `var` と `let` のより詳しい違いは、[var と let の違い](/ja/docs/Learn/JavaScript/First_steps/Variables#the_difference_between_var_and_let)を見てください。

変数を宣言したら、以下のように値を割り当てることができます。

```js
myVariable = 'Bob';
```

好みに応じて、両方の操作を同一の行で行うことができます。

```js
let myVariable = 'Bob';
```

変数の値は、名前で呼び出すだけで取得することができます。

```js
myVariable;
```

変数に値を代入した後で、変更することもできます。

```
let myVariable = 'Bob';
myVariable = 'Steve';
```

なお、変数は様々な[データ型](/ja/docs/Web/JavaScript/Data_structures)の値を保持することもできます。

| データ型                         | 説明                                                                                                                                         | 例                                                                                                                               |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| {{Glossary("String")}}     | 文字列と呼ばれる一連のテキスト。値が文字列であることを示すには、引用符で囲む必要があります。                                                 | `let myVariable = 'Bob';`                                                                                                        |
| {{Glossary("Number")}}     | 数。数字には引用符がありません。                                                                                                             | `let myVariable = 10;`                                                                                                           |
| {{Glossary("Boolean")}} | 論理値。 `true` と `false` は JS では特別なキーワードであり、引用符は必要ありません。                                                        | `let myVariable = true;`                                                                                                         |
| {{Glossary("Array")}}     | 単一の参照で複数の値を格納できる構造です。                                                                                                   | `let myVariable = [1,'Bob','Steve',10];` 配列の各メンバーはこのように参照してください。 `myVariable[0]`, `myVariable[1]`, など。 |
| {{Glossary("Object")}}     | 基本的には何でも格納できます。 JavaScript のすべてがオブジェクトであり、変数に格納することができます。学ぶ際にはこれを覚えておいてください。 | `let myVariable = document.querySelector('h1');` 上記の例も同様です。                                                            |

ではなぜ変数が必要なのでしょうか。何か面白いプログラミングをするには変数が必要です。値が変更できなければ、挨拶のメッセージをパーソナライズしたり、画像ギャラリーに表示されている画像を変更するなどの動的な操作ができないのです。

### コメント

コメントは、ブラウザーから無視される、コードの間に入れられた短いテキストスニペットです。CSS と同じように、JavaScript のコードではコメントを付けることができます。

```js
/*
挟まれているすべてがコメントです。
*/
```

コメントに改行が含まれていない場合、次のように 2 つのスラッシュの後ろに記載する方が簡単です :

```js
// これはコメントです
```

### 演算子

{{Glossary("operator", "演算子")}}は、2 つの値 (または変数) に基づいて結果を生成する数学的な記号です。次の表では、JavaScript コンソールで試してみるいくつかの例とともに、最も単純な演算子をいくつか見ることができます。

| 演算子           | 説明                                                                                                                                                                             | シンボル      | 例                                                                                                                                                                                                                                                                                                                                                          |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 加算/連結        | 2 つの数字を加えるか、2 つの文字列を結合します。                                                                                                                                 | `+`           | `6 + 9; 'Hello ' + 'world!';`                                                                                                                                                                                                                                                                                                                               |
| 減算、乗算、除算 | 基本的な数学の計算を実施します。                                                                                                                                                 | `-`, `*`, `/` | `9 - 3; 8 * 2; // JavaScript で乗算はアスタリスク 9 / 3;`                                                                                                                                                                                                                                                                                                   |
| 代入             | すでに出てきました。変数に値を割り当てます。                                                                                                                                     | `=`           | `let myVariable = 'Bob';`                                                                                                                                                                                                                                                                                                                                   |
| 等価             | 2 つの値と型が互いに等しいかどうかを調べ、`true`/`false` (論理値)の結果を返します。                                                                                              | `===`         | `let myVariable = 3; myVariable === 4;`                                                                                                                                                                                                                                                                                                                     |
| 否定、非等価     | その後にあるものと論理的に反対の値を返します。たとえば `true` を `false` に換えます。等価演算子と一緒に使用されると、否定演算子は 2 つの値が等しく*ない*かどうかをテストします。 | `!`, `!==`    | "Not" の場合、基本式は `true` ですが、それを否定しているので比較結果は `false` になります。`let myVariable = 3; !(myVariable === 3);`「等しくない」は、基本的に同じ結果を異なる構文で与えます。ここでは「`myVariable` が 3 とは等しくない」ことをテストします。 `myVariable` は 3 と等しいので、`false` を返します。`let myVariable = 3; myVariable !== 3;` |

他にも演算子はもっとたくさんありますが、今のところはこれで十分です。全体の一覧については、[式と演算子](/ja/docs/Web/JavaScript/Reference/Operators)を参照してください。

> **Note:** データ型を混在させると、計算を実行するときに奇妙な結果になる可能性があるため、変数を正しく参照し、期待通りの結果を得るように注意してください。例えばコンソールに `'35' + '25'` と入力してみてください。期待通りの結果にならないのはなぜでしょうか。引用符は数字を文字列に変換するので、数字を加算するのではなく、文字列を連結する結果になったのです。 `35 + 25` を入力すれば、正しい結果が得られます。

### 条件文

条件文は、ある式が true を返すかどうかをテストし、その結果次第でそれぞれのコードを実行するコード構造です。条件文のよくある形は `if ... else` 文です。例えば以下の通りです。

```js
let iceCream = 'チョコレート';
if(iceCream === 'チョコレート') {
  alert('やった、チョコレートアイス大好き！');
} else {
  alert('あれれ、でもチョコレートは私のお気に入り......');
}
```

`if( ... )` の中の式が条件です — ここでは等価演算子を使用して、変数 `iceCream` と`チョコレート`という文字列を比較し、2 つが等しいかどうかを調べています。この比較が `true` を返した場合、コードの最初のブロックが実行されます。比較が真でない場合、最初のブロックはスキップされ、 `else` 文の後にある 2 番目のコードブロックが代わりに実行されます。

### 関数

{{Glossary("Function", "関数")}} は、再利用したい機能をパッケージ化する方法です。プロシージャが必要なときは、毎回コード全体を書くのではなく関数名を使って関数を呼び出すことができます。すでにいくつかの関数の仕様を見てきました。例えば以下のようなものです。

```js
let myVariable = document.querySelector('h1');
```

```js
alert('hello!');
```

これらの関数、 `document.querySelector` と `alert` は、必要なときにいつでも使えるようブラウザーに組み込まれています。

もし変数名に見えるものがあったとしても、その後に括弧 `()` が付いていれば、おそらくそれは関数です。関数は普通、仕事をするのに必要な小さなデータである{{Glossary("Argument", "引数")}}を取ります。引数は括弧の中に入れ、複数の引数がある場合はカンマで区切ります。

例えば、 `alert()` 関数はブラウザーのウィンドウにポップアップボックスを表示しますが、ポップアップボックスに何を書き込むかを関数に指示するために、文字列を引数として渡す必要があります。

嬉しいことに、自分で関数を定義することができます。次の例では、引数として 2 つの数値をとり、それらを乗算するという単純な関数を記載します。

```js
function multiply(num1,num2) {
  let result = num1 * num2;
  return result;
}
```

上記の関数をコンソールで実行し、いくつかの引数を指定してテストしてみてください。例えば次のようなものです。

```js
multiply(4, 7);
multiply(20, 20);
multiply(0.5, 3);
```

> **Note:** [`return`](/ja/docs/Web/JavaScript/Reference/Statements/return) 文は `result` の値を関数内から関数の外に戻すことをブラウザーに指示し、それを利用できるようにします。これが必要な理由は、関数内で定義された変数が、その関数内でしか利用できないためです。これは変数の{{Glossary("Scope", "スコープ")}}と呼ばれています([変数のスコープのより詳しい説明](/ja/docs/Web/JavaScript/Guide/Grammar_and_types#variable_scope)をお読みください)。

### イベント

ウェブサイトを実際にインタラクティブにするには、イベントが必要です。イベントは、ブラウザーの中で起きていることを検出し、その応答としてコードを実行するコード構造です。最も分かりやすい例は [click イベント](/ja/docs/Web/API/Element/click_event)で、マウスで何かをクリックするとブラウザーによって発行されるものです。これを実行するには、コンソールに以下のように入力してから、現在のウェブページ上をクリックしてください。

```js
document.querySelector('html').onclick = function() {
    alert('痛っ! つつくのはやめて!');
}
```

要素にイベントを割り当てる方法はたくさんあります。ここでは {{htmlelement("html")}} 要素を選択し、[`onclick`](/ja/docs/Web/API/GlobalEventHandlers/onclick) ハンドラープロパティに、クリックイベントで実行したいコードを含む無名 (つまり名前がない) 関数を代入します。

なお、

```js
document.querySelector('html').onclick = function() {};
```

は以下のものと同等です。

```js
let myHTML = document.querySelector('html');
myHTML.onclick = function() {};
```

短くしただけです。

## ウェブサイトの例を膨らませる

さて、 JavaScript の基本のおさらいが終わったところで、例題のサイトに新しい機能を追加してみましょう。

先に進む前に、 `main.js` ファイルの現在の内容を削除して、空のファイルを保存してください。そうしないと、 "Hello world!" の例で使用した既存のコードが、これから追加する新しいコードと衝突してしまいます。

### 画像の切り替えの追加

このセクションでは、 DOM API 機能をもっと使用して、サイトに画像を追加しましょう。画像をクリックすると JavaScript を使用して 2 つの画像を切り替えることができます。

1. まずサイトに掲載したいと思う別な画像を見つけてください。最初の画像と同じサイズか、できるだけ近いものを使用してください。
2. この画像を `images` フォルダーに保存してください。
3. この画像の名前を _firefox2.png_ に変更してください。
4. `main.js` ファイルに次の JavaScript を入力してください。

    ```js
    let myImage = document.querySelector('img');

    myImage.onclick = function() {
        let mySrc = myImage.getAttribute('src');
        if(mySrc === 'images/firefox-icon.png') {
          myImage.setAttribute('src','images/firefox2.png');
        } else {
          myImage.setAttribute('src','images/firefox-icon.png');
        }
    }
    ```

5. `index.html` をブラウザーに読み込みます。画像をクリックすると、もう一方の画像に変わります。

{{htmlelement("img")}} 要素への参照を変数 `myImage` に格納します。次にこの変数の `onclick` イベントハンドラープロパティに、名前のない関数(無名関数)を代入します。そうすれば、この要素がクリックされるたびに以下の動きをします。

1. 画像の `src` 属性の値を取得します。
2. 条件文を使って、`src` の値が元の画像のパスと等しいかどうかをチェックします。

    1. そうであれば、`src` の値を 2 番目の画像へのパスに変更し、もう一方の画像が強制的に {{htmlelement("img")}} 要素の中に読み込まれるようにします。
    2. そうでない (すでに変更されている) 場合、`src` の値を元の画像のパスに戻して、元の状態に戻ります。

### パーソナライズされた挨拶メッセージの追加

次に、もう 1 つの小さなコードを追加し、ユーザーがサイトにアクセスしたときに、ページの表題をパーソナライズされた挨拶メッセージに変更してみましょう。この挨拶メッセージは、ユーザーがサイトを離れて後で戻った時にも保存されるようにします。[Web Storage API](/ja/docs/Web/API/Web_Storage_API) を使用して保存しましょう。したがって、必要な時にいつでもユーザーと挨拶メッセージを変更できるオプションも用意しましょう。

1. `index.html` では、 {{htmlelement("script")}} 要素の直前に次の行を追加します。

    ```html
    <button>ユーザーを変更</button>
    ```

2. `main.js` では、次のコードを下記のとおりにファイルの最後に配置します。これは新しいボタンと見出しへの参照を変数に格納します。

    ```js
    let myButton = document.querySelector('button');
    let myHeading = document.querySelector('h1');
    ```

3. パーソナライズされた挨拶を設定する以下の関数を追加しましょう。まだ何も起こりませんが、すぐに修正します。

    ```js
    function setUserName() {
      let myName = prompt('あなたの名前を入力してください。');
      localStorage.setItem('name', myName);
      myHeading.textContent = 'Mozilla はすばらしいよ、' + myName;
    }
    ```

    この関数では [`prompt()`](/ja/docs/Web/API/Window/prompt) 関数を使用して、`alert()` のようにダイアログボックスを表示しています。しかし、`prompt()` は `alert()` とは異なり、ユーザーにデータを入力するよう求め、ユーザーが **OK** を押した後に変数にそのデータを格納します。この場合、ユーザーに名前を入力するよう求めます。次に、`localStorage` と呼ばれる API を呼び出すことで、ブラウザーにデータを格納して後で受け取ることができます。 localStorage の `setItem()` 関数を使って、`'name'` と呼ばれるデータを作成し、 `myName` に入っているユーザーから入力されたデータを格納します。最後に、見出しの `textContent` に文字列と新しく格納されたユーザーの名前を設定します。

4. 次に、この `if ... else` ブロックを追加します。これは初期化コードと呼ぶことができ、最初の読み込みでアプリを構成します。

    ```js
    if(!localStorage.getItem('name')) {
      setUserName();
    } else {
      let storedName = localStorage.getItem('name');
      myHeading.textContent = 'Mozilla はすばらしいよ、' + storedName;
    }
    ```

    このブロックでは、最初に `name` のデータが存在しているかどうかをチェックするために否定演算子 (! で表される論理否定) を使用しています。存在しない場合は、作成するために `setUserName()` 関数が実行されます。存在する場合は (つまり、以前の訪問時にユーザーが設定した場合)、 `getItem()` を使用して格納された名前を受け取り、 `setUserName()` の中で行ったのと同様に、見出しの `textContent` に文字列とユーザーの名前を設定します。

5. 最後に、以下の `onclick` イベントハンドラーをボタンに設定します。クリックすると、`setUserName()` 関数が実行されます。これでユーザーがボタンを押すことで、好きな時に新しい名前を設定できるようになります。

    ```js
    myButton.onclick = function() {
      setUserName();
    }
    ```

### A user name of null?

この例を実行してユーザー名を入力するダイアログボックスが出たとき、*キャンセル*ボタンを押してみてください。結果として "Mozilla is cool, null" というタイトルが表示されるでしょう。これはプロンプトをキャンセルしたときに、値が [`null`](/ja/docs/Web/JavaScript/Reference/Global_Objects/null)、つまり値がないことを示す JavaScript の特殊な値に設定されるためです。

また何も入れずに _OK_ を押してみてください — 結果として "Mozilla is cool," というタイトルが表示され、これは理由が明白です。

この問題を避けるには、ユーザーーが `null` や空白の名前を入力していないかチェックするよう、`setUserName()` 関数を書き換えます。

```js
function setUserName() {
  let myName = prompt('Please enter your name.');
  if(!myName) {
    setUserName();
  } else {
    localStorage.setItem('name', myName);
    myHeading.textContent = 'Mozilla is cool, ' + myName;
  }
}
```

人間の言語では — `myName` に値がない場合や、`null`の場合、 最初から `setUserName()` を実行します。値がない場合 (上記の式が真でない場合)には、`localStorage` に値をセットして、見出しのテキストにもセットします。

## まとめ

最後までこの記事の手順に従った場合は、最終的に次のようなページが表示されているでしょう ([こちらで作成した版を表示する](https://mdn.github.io/beginner-html-site-scripted/)こともできます)。

![](website-screen-scripted.png)

行き詰まったら、自分の作業を [Github 上の完成したサンプルコード](https://github.com/mdn/beginner-html-site-scripted/blob/gh-pages/scripts/main.js)と比べてみてください。

私たちは JavaScript に少し触れただけです。楽しく遊んだり、もっと上達したい場合は、[JavaScript の学習トピック](/ja/docs/Learn/JavaScript)に進んでください。

## 関連情報

- [JavaScript による動的なクライアント側スクリプト](/ja/docs/Learn/JavaScript)
  - : もっと詳細な JavaScript に飛び込みましょう。
- [Learn JavaScript](https://learnjavascript.online/)
  - : ウェブ開発者を目指す方に最適な教材です! インタラクティブな環境で、短いレッスンとインタラクティブなテスト、自動評価によるガイドで、 JavaScript を学ぶことができます。最初の 40 レッスンは無料です。全コースは少額の一括払いでご利用いただけます。

{{PreviousMenuNext("Learn/Getting_started_with_the_web/CSS_basics", "Learn/Getting_started_with_the_web/Publishing_your_website", "Learn/Getting_started_with_the_web")}}

## このモジュール

- [基本的なソフトウェアのインストール](/ja/docs/Learn/Getting_started_with_the_web/Installing_basic_software)
- [ウェブサイトをどんな外見にするか](/ja/docs/Learn/Getting_started_with_the_web/What_will_your_website_look_like)
- [ファイルの扱い](/ja/docs/Learn/Getting_started_with_the_web/Dealing_with_files)
- [HTML の基本](/ja/docs/Learn/Getting_started_with_the_web/HTML_basics)
- [CSS の基本](/ja/docs/Learn/Getting_started_with_the_web/CSS_basics)
- [JavaScript の基本](/ja/docs/Learn/Getting_started_with_the_web/JavaScript_basics)
- [ウェブサイトの公開](/ja/docs/Learn/Getting_started_with_the_web/Publishing_your_website)
- [ウェブのしくみ](/ja/docs/Learn/Getting_started_with_the_web/How_the_Web_works)

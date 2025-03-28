---
title: MDN にリンクするには
slug: orphaned/MDN/About/Linking_to_MDN
original_slug: MDN/About/Linking_to_MDN
---
{{MDNSidebar}}

MDN にリンクするガイドラインやそもそもリンクして良いのか聞かれることがありますが、もちろん **OK です。MDN にリンクして頂いて構いません。**その際のガイドラインやベストプラクティスが必要であれば続けて読んでください。

## MDN にリンクして良いですか？

**はい！**是非どうぞ！ハイパーテキストリンクは Web の本質的な機能であるだけでなく、ユーザに価値あるリソースを指し示す方法であると共に、私たちのコミュニティの成果に対する信頼を示すことでもあります。

ですから、MDN のコンテンツへのリンクは是非遠慮なくしてください。[MDN のフロントページ](/)、あるいは必要に応じて MDN 内の特定ページにリンクしてください。リンク先ページ選択のベストプラクティスは以下の通りです。

## どのページにリンクすべきですか？

リンクすべき特定のページは決まっていません。**あなたの読者に役立つのがどのページか**というのが大事です。

- MDN 自体について書かれている時はメインページにリンクしていただけます: [https://developer.mozilla.org/](/)
- 特定領域や技術について言及される場合は特定のトピックについて目次や索引となる**ランディングページ**と呼ばれるページにリンクするのが良いでしょう。例えばこのようなページです:

  - HTML: [https://developer.mozilla.org/ja/docs/Web/HTML](/ja/docs/Web/HTML)
  - HTML5: [https://developer.mozilla.org/ja/docs/Web/Guide/HTML/HTML5](/ja/docs/Web/Guide/HTML/HTML5)
  - CSS: [https://developer.mozilla.org/ja/docs/Web/CSS](/ja/docs/Web/CSS)
  - CSS3: [https://developer.mozilla.org/ja/docs/Web/CSS/CSS3](/ja/docs/Web/CSS/CSS3)
  - DOM: [https://developer.mozilla.org/ja/docs/Web/API/Document_Object_Model](/ja/docs/Web/API/Document_Object_Model)
  - JavaScript: [https://developer.mozilla.org/ja/docs/Web/JavaScript](/ja/docs/Web/JavaScript)

- 特定のページや技術などについて書かれている場合は個別のページにリンクするのが良いでしょう。例えば:

  - HTML の要素について説明しているなら、HTML 要素リストページ ([https://developer.mozilla.org/ja/docs/Web/HTML/Element](/ja/docs/Web/HTML/Element)) や {{HTMLElement("colgroup")}} など個別要素のページ
  - 同様に CSS についても CSS リファレンス (網羅的な目次ページ: [https://developer.mozilla.org/ja/docs/Web/CSS/Reference](/ja/docs/Web/CSS/Reference)) や {{cssxref("list-style-type")}} といった特定プロパティのページ

**いずれにしても、リンク元ページや読者にとって最適なページにリンクしてください。**リンクや私たちではなく、読者こそが大事なのですから。

## 良いリンクの仕方は？

リンクの仕方は自明ですが、良いリンクの仕方は少々難しいこともあります。リンクの仕方はいくつかあります:

### テキスト内でのリンク

これが最も便利なリンク方法です。特定の話題に対して読者に更なる情報をリンクで提供するのです。多くの場合、このようなリンクはユーザを個別の関連情報ページにリンクするもので、Web サイトのホームページにリンクするものではありません (例外もありますが)。

> … [IndexedDB](/ja/docs/IndexedDB) API を使えば、ローカルのデータベースにデータを格納できます…

このようなリンクはワンクリックでより詳しい情報が得られるユーザにとっても、的確な文脈で紹介してくれたことで気に入ってもらえるだろう MND にとっても、両方にとってとても価値あるものです。私たちのミッションは読者にできる限り速やかに必要な情報を届けることで、これは明らかにステキなやり方です。

#### テキスト中のリンクで避けるべきこと

テキスト中のリンクはステキで便利なものですが、留意すべき事がいくつかあります:

- **リンクしすぎないこと。**[す](/ja/docs/Web/JavaScript/Reference/Statements/do...while "do...while") [べ](/ja/docs/Web/CSS/:not ":not()") [て](/ja/docs/Web/CSS/:link ":link") の単語、あるいはほぼすべての文字にリンクをつけるのは目障りです。文章の中で大事な部分だけをしっかり選んでそこだけリンクするか、読者が既に知っていそうな事についてまでリンクしないようにすること。
- **同じ用語について何度も繰り返しリンクしない。** 例えば CSS アニメーションについて各場合、「アニメーション」という単語がでてくるたびに [`animation` CSS プロパティ](/ja/docs/Web/CSS/animation) にリンクする必要はありません。読者はそれについて知らなければ、最初にでてきたときに関連情報へのリンクをクリックします。それ以降の部分では、以前から知っていたか前出時にリンク先を見て知ったかに関わらず、すでに知っている前提で書き進めることができます。読者がリンク先を参照するためにページをスクロールせずに済むように、同じ用語について何度か (多くとも数段落毎に一度) リンクするのは構いません。
- **フォーラムやブログコメントでリンクするときにはご注意を。**具体的な質問や問題に対して適切な情報源に関連リンクを示すのはステキだし歓迎されます。Web 上のあちこちに MDN へのリンクを無闇に書きまくるのは不適切です。サイトの管理者や読者は速やかにあなたをスパマーとして認識し、MDN の評価が傷つけられます。私たちは価値あるリソースを作ることに努めておりそのような行為によって私たちの努力の成果が損なわれることは望んでいません。適切な数だけ関連するリンクを紹介してください。

### バナーや画像をサイトに追加するには

本文中からのリンク以外に、例えばサイドバーの画像から MDN にリンクしていただくこともできます。テキスト中のリンクはあなたが読者に情報を保管する目的でリンクするものですが、この場合は意味合いが異なります。サイドバーなどにリンク画像を追加するのは、あなたの MDN プロジェクトへの支援を表明するものであったり、MDN を宣伝するものであったり、総合的な情報源として MDN を紹介するものになります。

支援を表明するのに遠慮しないでください。[MDN を宣伝するには](/docs/MDN/Promote) ページであなたのサイトに合わせたボタンを作ってください。ランディングページなど他のページへのリンクにしていただくのも自由です。

### WordPress から MDN に自動リンクするには

ブログポストから用語を選んで MDN の適切なページに自動的にリンクする [WordPress plugin](/docs/MDN/Promote#WordPress_plugin) を用意しています。このプラグインでは上記のガイドラインに沿ったかたちでリンクしながら Web 技術についてブログを書るよう助けてくれます。試しにインストールしてみて、良ければご利用ください。

ご支援ありがとうございます！

## Cross-Origin Resource Sharing

私達は MDN の公開する全てのデータで [CORS](https://developer.mozilla.org/docs/HTTP/Access_control_CORS "/docs/HTTP/Access_control_CORS") を有効にしているつもりです。これにはほぼ全てのものが当てはまるはずです。もしあなたがなにか[cross-origin requests](https://developer.mozilla.org/docs/HTTP/Access_control_CORS "/docs/HTTP/Access_control_CORS")が使えない状態を発見したら、それは[修正すべきバグ](https://bugzilla.mozilla.org/form.mdn)です。

<header></header>

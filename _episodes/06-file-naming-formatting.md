---
title: File naming & formatting（ファイル名とフォーマット）
teaching（講義）: 30
exercises（演習）: 10
questions（課題）:
- What best practices and generic skills can be used to successfully use and create library related programs?
- 図書館に関するプログラムを上手く利用および作成するための最適なやり方と一般的なスキルは何ですか？
objectives（目的）:
- Identify best practices in naming and structuring files.
- ファイル命名と構造化のベストプラクティスを確認する。
- Identify best practices in using software and data.
- 使用するソフトウェアとデータにおけるベストプラクティスを確認する。

keypoints（キーポイント）:
- Data structures should be consistent and predictable.
- データ構造は一貫性と予測可能であるべき。
- Consider using semantic elements or data identifiers to data directories.
- データディレクトリには意味的要素やデータ識別子の使用を検討する。
- Fit and adapt your data structure to your work.
- データ構造を作業に適合させること。
- Apply naming conventions to directories and file names to identify them, to create associations between data elements, and to assist with the long term readability and comprehension of your data structures.
- ディレクトリとファイル名に命名規則を適用して、それらを識別し、データ要素間を関連付け、データ構造の長期的な可読性と理解を支援する。
---

## Names matter（名前は大事）

We are all guilty of naming our files in such a way that sometimes we have a hard time finding them. For example, the following XKCD comic may be all too familiar.
私たちはみな、このようなファイル名を付けてしまいがちで、探すのに時間がかかる。たとえば次のXKCDコミックはあまりに有名かもしれない。

![Protip: Never look in someone else's documents folder](../files/someone_elses_documents_folder.png)

'Protip: Never look in someone else's documents folder.' by Randall Munroe available at [https://xkcd.com/1459/](https://xkcd.com/1459/) under a Creative Commons Attribution-NonCommercial 2.5 License.
「アドバイス：他人のフォルダをのぞいてはいけません」

There are a number of other [bad file naming examples catalogued by Twenty Pixels](http://20px.com/blog/2015/07/16/catalogue-bad-file-naming/) such as the _Overly Underscored_ or _Signs of Frustration_. Do any of these examples look familiar?
悪い名前を付け方がまとめられています。無題テキスト、、、なんとか削除、なんとか無効、なんとか最終版、、、アンダーバー使いすぎ、いらだちをしめすなど。これらの例に見覚えがありますか？

The [File Organisation: Naming](https://datacarpentry.org/rr-organization1/01-file-naming/index.html) episode of Data Carpentry's Reproducibility of Research lesson contains principles and examples that we can apply to finding and working with files that will save us time later. For example, [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601), the preferred format for dates: YYYY-MM-DD. It introduces best practices such as using special case styles, 'Kebab-case' and 'Snake_case'. Dryad has additional [guidance on creating reusable data packages](https://datadryad.org/stash/best_practices) including folder and file structure.
姉妹版に研究の再現性、ファイル名の名前付けというセッションがある。悪い例とかいい例とか。データカンペントリーの方のレッスン。あとからファイルを見つけやすくなって、時間の節約できるような例
ISO 8601のような日付の書き方。YYYY-MM-DD(年4桁-月2桁-日2桁)。特殊なケーススタイル、ケバブケース（ハイフン）、スネークケース（アンダーバー）、ドライアドに説明がある。

## Naming files sensible things is good for you and for your computers
注意して名前をつけるのはあなたにもコンピュータにもいいこと。

Working with data is made easier by structuring your files in a consistent and predictable manner. Without structured information, our lives would be much poorer. As library and archive people, we know this. But let's linger on this a little longer because for working with data it is especially important.
データを使って仕事をするときには、あなたのファイルを一貫性のある予期できる方法でこのデータを構造化すると仕事をするのが簡単になります。構造化された情報がなかったら私達の生活は貧しく、不便になります。私は図書館やアーカイブで働いているので、知っているはずです。

Examining URLs is a good way of thinking about why structuring data in a consistent and predictable manner might be useful in your work. Good URLs represent with clarity the content of the page they identify, either by containing semantic elements or by using a single data element found across a set or majority of pages.
しかしもう少し細かくみていきましょう。データで仕事をするのはすごく重要なことだからです。URLを調べるというのはデータが一貫性があって予期できるかのよい方法です。よいURLはウェブページに載っている情報の中身をはっきり示すものです。それは意味的な要素を示している単一の情報を複数のページをまたいだ一つの要素を含んでいるからです。

A typical example of the former are the URLs used by news websites or blogging services. WordPress URLs follow the format:
よくある意味的な情報を含むURLの例。ニュースとかブログ

-   `ROOT/YYYY/MM/DD/words-of-title-separated-by-hyphens`
-   <https://cradledincaricature.com/2015/07/24/code-control-and-making-the-argument-in-the-humanities/>
ルート/年/月/日/タイトルをハイフンで区切る

A similar style is used by news agencies such as a *The Guardian* newspaper:
同様な例、新聞社

-   `ROOT/SUB_ROOT/YYYY/MMM/DD/words-describing-content-separated-by-hyphens`
-   <https://www.theguardian.com/uk-news/2014/feb/20/rebekah-brooks-rupert-murdoch-phone-hacking-trial>
ルート/サブルート/年/月/日/コンテンツの説明、ハイフン

In data repositories, URLs structured by a single data element are often used. The National Library of Australia's TROVE uses this format:
データリポジトリでは単一の要素で使われる

-   `ROOT/record-type/REF`
-   <https://trove.nla.gov.au/work/6315568>
-   ルート/レコードタイプ/レファレンス番号

The Old Bailey Online uses the format:

-   `ROOT/browse.jsp?ref=REF`
-   <https://www.oldbaileyonline.org/browse.jsp?ref=OA16780417>

What we learn from these examples is that a combination of semantic description and data elements make for consistent and predictable data structures that are readable both by humans and machines. Transferring this kind of pattern to your own files makes it easier to browse, to search, and to query using both the standard tools provided by operating systems and by the more advanced tools Library Carpentry will cover.
これらからわかるのは意味的な説明とデータの要素の組み合わせというのは人間と機械の両方に読みやすくします。こういった例を自分にあてはめるとファイルをブラウズしやすくなったり検索しやすくなったり、これから説明、OSの機能、スタンダードツールで閲覧や検索がしやすくなります。

In practice, the structure of a good archive might look something like this:
実際にはよいアーカイブという方法

- A base or root directory, perhaps called 'work'.
- ベースはルートディレクトリ、おそらくwork
- A series of sub-directories such as 'events', 'data', ' projects', etc.
- サブディレクトリ
- Within these directories are series of directories for each event, dataset or project. Introducing a naming convention here that includes a date element keeps the information organised without the need for subdirectories by, say, year or month.
- データセット、プロジェクト、年月日などをつけたファイル名を作って、そこから先は年とか月とかでサブディレクトリを作らない、こうするとあとから自分が何をしていたか思い出しやすくなります。
- これを実世界上の保存ということになります。

All this should help you remember something you were working on when you come back to it later (call it real world preservation).

The crucial bit for our purposes, however, is the file naming convention you choose. The name of a file is important to ensuring it and its contents are easy to identify. `Data.xslx` doesn't fulfill this purpose. A title that describes the data does. And adding dating convention to the file name, associating derived data with base data through file names, and using directory structures to aid comprehension strengthens those connections.
重要な点はあなたが決めたファイルの規則です。Data.xslx(xlsx?)はこの目的を満たしません。ファイルのタイトルは目的に合います。日付の規則をファイル名に追加する。まとめやすくサブディレクトリを作って、ファイル間のつながりが強くなります。

## Plain text formats are your friend
## プレーンテキストはあなたの友達です。

Why? Because computers can process them!
なぜならコンピュータで処理できるからです。

If you want computers to be able to process your stuff, try to get in the habit where possible of using platform-agnostic formats such as `.txt` for notes and `.csv` (comma-separated values) or `.tsv` (tab-separated values) for tabular data. TSV and CSV files are both spreadsheet formats. These plain text formats are preferable to the proprietary formats (e.g., Microsoft Word)  because they can be opened by many software packages and have a strong chance of remaining viewable and editable in the future. Most standard office suites include the option to save files in `.txt`, `.csv`, and `.tsv` formats, meaning you can continue to work with familiar software and save your files in the more perennial formats. Compared to `.doc` or `.xls`, these formats have the additional benefit of containing only machine-readable elements. 
もしコンピュータに処理させようと思ったら、プラットフォームに依存しないフォーマットを利用しましょう。.txt .csv　カンマ区切りテキスト .tsv　タブ区切りテキスト
どちらもスプレッドシートのフォーマット、これらのテキストフォーマット、独占的なフォーマット（例えばWordみたいなフォーマット）より好まれます。
いろんなソフトで開ける。参照や編集もできるからです。たいていのOfficeのフォーマットは保存するオプションがあって、あなたのよくなれたソフトウェアでそれらを編集することができますし、
他のフォーマットでできることもできます。.doc.xlsと比べるとマシンリーダブルという特徴があります。

When working with files for automation or computational purposes, it is more important to focus on meaningful transmission of data as opposed to fancy formatting. Whilst using bold, italics, and colouring to signify headings or to make a visual connection between data elements is common practice, these display-orientated annotations are not (easily) machine-readable and hence can neither be queried and searched nor are appropriate for large quantities of information. One rule of thumb is if you can't find it by <kbd>Ctrl</kbd>+<kbd>F</kbd>/<kbd>Command</kbd>+<kbd>F</kbd> it isn't machine readable. Preferable are simple notation schemes such as using a double-asterisk or three hashes to represent a data feature: for example, we could use three question marks to indicate something that needs follow up, chosen because `???` can easily be found with a <kbd>Ctrl</kbd>+<kbd>F</kbd>/<kbd>Command</kbd>+<kbd>F</kbd> search.
自動化とかコンピュータで処理しようとすると、この見た目をきれいにするのではなく、意味のある形にするということがとても重要です。例えば、太字にするとかイタリックにするとか色をつける強調するデータの間に見た目のコネクション関連するとかよくやられていますが、視覚上での注意書きは簡単には機械は読めない。読めないし、こういう強調とか関係とか機械で読めないから検索できない。検索できないので大量のデータを扱うのに向いていません。簡単にいえな、コントロールFでみえないものはマシンリーダブルではありません。好まれるのは簡単な注書きを書く仕組み。例えばアスタリスク2つとかシャープ3つとか
データを表現するのに好まれます。例えば私達はクエスチョンマーク3つを注意を促すことができます。簡単に検索できます。

## Use machine readable plain text notation for formatting
機械が処理できる見た目を整理するためのテキストノーテーション

There are some simple notation schemes that are also plain text and machine readable, but can be used to render simple formatting. One such scheme is called Markdown, a lightweight markup language. A markup language is a metadata language that uses notation to distinguish between the content and the formatting of the content. Markdown files, which use the file extension `.md`, are machine and human readable. Markdown applications can be disparate, from simple to-do lists, to extensive manual pages. For example, GitHub renders text via Markdown. For instance, you can inspect the [underlying Markdown for this episode, File naming & formatting](https://github.com/LibraryCarpentry/lc-overview/blob/gh-pages/_episodes/06-file-naming-formatting.md).
簡単なノーテーションの仕組み。表記法はいくつかあります。見た目を整えるためにも使います。マークダウン、軽量マークアップ言語の一つ。メタデータランゲージ。コンテンツ、中身とその中身のフォーマッティング見た目を区別するための表記法。マークダウン。mdは機械可読でもあるし、人間可読でもある。マークダウンを使ったアプリケーション。To Doリスト。マニュアル。いろんなものがあります。例えば、Githubはテキストのフォーマットができます。実際これがマークダウン、Github上ではこういう風になる。

> ## How can I format a Markdown file?
>
> There are a number of ways we can do this, for instance [hackmd.io](https://hackmd.io/) or [cryptpad.fr/code](https://cryptpad.fr/code), we will use [Dillinger.io](https://dillinger.io/) referenced in the [Markdown Guide](https://www.markdownguide.org/). Go to Dillinger.io and change the headings to bold.
>
> > ## Answer
> >
> > To bold text you can either use `**bold text**` or  `__bold text__`.
> > 
> {: .solution}
{: .challenge}

マークダウンってどうやってつくるの？
書き方ガイドっていくつかあります。もうちょっといろんな例があります。
csvをマークダウンに変換する

The [Markdown Guide](https://www.markdownguide.org/) is a helpful resource for learning Markdown but you can also try:

- [CommonMark's guide](https://commonmark.org/help/)
- [Mastering Markdown](https://guides.github.com/features/mastering-markdown/). 
- [Markdown Here Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Here-Cheatsheet). 

For more advanced Markdown examples, the internet can be a helpful resource. For instance, if you need to convert a `.csv` table to a `.md` table you can find helpful resources such as [Convert CSV to Markdown](http://www.convertcsv.com/csv-to-markdown.htm).

The following resource provides further background on Markdown for people in library- and information-related roles:   
Ovadia, Steven. "[Markdown For Librarians And Academics.](https://academicworks.cuny.edu/cgi/viewcontent.cgi?article=1006&context=lg_pubs)" Behavioral & Social Sciences Librarian 33.2 (2014): 120-124.

ライブラリアンとアカデミックスのためのマークダウン

## Applications for writing, reading and outputting plain text files

どんなソフトを使って作業するのか

We've already discussed why plain text formats are needed for working with data, and it's also important to understand that you need different tools to work with these formats. Word processors like Microsoft Word, LibreOffice Writer, and Google Docs will explicitly _not_ work for this purpose -- those tools are meant to optimize how documents appear to humans, not to computers. They add many hidden characters and generally are unsuitable for working with plain text files. The category of tool you'll want to use for data is called a _text editor_. Text editors save only the text that you type -- there is no hidden formatting or metadata. What you see in a text editor is what a computer will see when it tries to process that data.       

ワードプロセッサーアプリケーション、Microsoft Word、Libre Office Google Docs、人間向けに最適化されていて、コンピュータ向けには不向きです。
Wordとかは隠れた文字を追加してしまいます。プレーンテキストでやるには向いていません。テキストエディタといわれるものです。あなたの打った文字だけを保存します。隠れたメタデータ、隠れた文字列は保存しません。

Two free, cross-platform editors that work well for handling plain text files are [Visual Studio Code](https://code.visualstudio.com/) and [Atom](https://atom.io/). For Windows users, [Notepad++](http://notepad-plus-plus.org/) is recommended. Mac or Unix users may find [Komodo Edit](https://www.activestate.com/products/komodo-ide/downloads/edit/), [Kate](https://kate-editor.org/) or [Gedit](https://wiki.gnome.org/Apps/Gedit) useful.
Combined with [pandoc](http://pandoc.org/), a Markdown file can be exported to PDF, HTML, a formatted Word document, LaTeX or other formats, so it is a great way to create machine-readable, easily searchable documents that can be repurposed in many ways. This [Programming Historian](https://programminghistorian.org/) [tutorial](https://programminghistorian.org/en/lessons/sustainable-authorship-in-plain-text-using-pandoc-and-markdown) spells out what to do.

ここで2つクロスフォーマットで使えて、プレーンテキストを使える。Visual Stuidio Code、Atom。Windows Notepad++もおすすめです。MacやUNIX、komodo、Kate、（日本語圏ではまた別）
LateXとか色々な
機械が読めて検索できる、いろんな方法に再利用できる。Programming　Historian、マークダウンとPandocを使ってPDFを作る。

In [Library Carpentry: The UNIX Shell](https://librarycarpentry.org/lc-shell/) lesson, we all see how the command line can be a powerful tool for working with text files.

Unix Shellでコマンドラインを使ってテキストファイルの処理をする方法を学んでいきます。

# 1. Dillinger
markdownやDillingerに関する説明。

__2021年11月2日追記：Dillingerでは、日本語フォントを含むmd.ファイルをpdfに変換すると、文字化けする？回避方法は[下記参照](#chapter5)。__


## markdownとは
HTMLは、ウェブページ作成のための言語である。

インターネットの利用が当然となっているため、
手順書などを共有するとき、文書ファイルのドキュメントをサーバーに保存するのではなく、
ウェブページでまとめ、社内wikiなど見やすい状態でブラウザ上で情報を共有するケースが増えている。

しかしながら、HTMLは複雑な記法が多く、利用するのはウェブ系エンジニアに限定されていた。

一方、markdownは、簡潔な記法であり、HTMLに変換する言語である。

このため、近年ではmarkdownとクラウドサービスを連携させることで、ファイルや情報の共有が、素人でも可能になっている。

この文書では、Dillingerを使い、markdownを記述する手順を記す。

## Dillingerの特徴
- ソフトウェアのインストールが不要で、ブラウザ上でmarkdownを執筆できる。
- markdownで執筆しながら、出力画面をオンラインプレビューできる。
- ローカルマシンやクラウドサービスへのファイルの保存・エクスポート、pdf出力などが可能。
- 無料。

## Dillingerの機能
下記では、[Dillinger][url1]の画面にあるボタンの機能を説明する。

   [url1]: <https://dillinger.io/>

- Document name：直接、markdownファイル名（.md）を編集できる。
- PREVIEW AS：ブラウザの別タブに、HTMLやpdfとしてプレビュー画面を出力する。
- EXPORT AS：markdownファイル（.md）をHTMLやpdfに変換したファイルを、ローカルに保存する。
- SAVE TO：markdownファイル（.md）をクラウドサービスに保存する。
- IMPORT FROM：ローカルやクラウドサービスから、markdownファイル（.md）をインポートする。


# 2. markdownの記法
markdownでは、文字装飾、タイトル付け、箇条書き、表作成、画像挿入、URLのハイパーリンクなどが可能である。
[Markdown site][url2]や他のwikiなどを参照。

   [url2]: <https://backlog.com/ja/blog/how-to-write-markdown/>



# 3. クラウドサービスとの連携
公式サイトでは、DillingerはDropbox、Bitbucket、Github、Google Drive、One Driveのクラウドサービスと連携できる、と書いてある。

しかし、下記の理由から、**Dropbox**と連携するのが一番利便性が良いと考えられる。
- 社内では、Google Drive（Googleアプリ系）が公式で利用できない（社内用gmail発行の申請が必要）
- 社内では、One Driveは社内公式用を課金制で利用できる
- Githubは、なぜか連携できなかった
- Bitbucketは、使ったことないからよく知らない、怖い


## Dropboxと連携させた使い方
- mdファイルの編集：Dillinger
- pdf出力："PREVIEW AS"でブラウザ上に出力
- pdf保存："EXPORT AS"でローカルに保存（その後、手動でDropboxにアップロード）
- mdファイルの保存："SAVE TO"でDropboxに保存
- mdファイルのインポート："IMPORT FROM"でDropboxからインポート

## ローカルのみの使い方
- mdファイルの編集：Dillinger
- pdf出力："PREVIEW AS"でブラウザ上に出力
- pdf保存："EXPORT AS"でローカルに保存
- mdファイルの保存："EXPORT AS"でローカルに保存
- mdファイルのインポート："IMPORT FROM"でローカルからインポート


# 4. Dropboxとの連携方法
Dropboxとの連携方法を下記に示す。

## 手順1
Google chromeか、Microsoft Edgeで[Dropbox][url3]を開く。

   [url3]: <https://www.dropbox.com>

Dropboxのアカウントを作成する。

社内メールアドレスよりも、スマホで私用gmailアドレスを取得して登録するほうが認証が楽。

## 手順2
[Dillinger][url1]でDropboxと連携させる。

Dillinger画面左上のボタンを押し、"SERVICES"から"Link with Dropbox"を押す。

DropboxのAPI認証をする。

連携できていれば、"Link with Dropbox"が"Unlink Dropbox"に変わっている。

## 手順3
Dillingerで、mdファイル（.md）名を変更したり、内容を編集する。

## 手順4
mdファイル（.md）をDropboxに保存する。

"SAVE TO"で"Dropbox"を選択する。

Dropbox側のホームに、"Dillinger"というフォルダが作成されており、そのフォルダにmdファイルが保存される。
（このフォルダがDillingerとの連携フォルダ）

**ただし、連携フォルダに同じ名前のmdファイルがすでにある場合は上書き保存されるので、保存前にはファイル名に注意すること。**

## 手順5
別のmdファイルをテンプレートにして、編集する。

"IMPORT FROM"で"Dropbox"を選択する。

Dropbox連携フォルダ内から、インポートするmdファイルを選択すると、インポートされる。

**Dillingerの"DOCUMENT NAME"から、ファイル名を変更する。**（そのまま保存すると、テンプレートが上書き保存されてしまう）

それ以降は手順3、4に従えば良い。


<a id="chapter5"></a>
# 5. 日本語フォントを含むpdf変換（2021年11月2日追記）
Dillingerは、pdfへのエクスポート機能を持つが、日本語を含むmdファイルをエクスポートしたpdfでは、文字化けした。

原因を調べたが、これを直接回避する方法は見つかっていない。（Viewerでは問題なかったが、pdf変換設定がどうやら対応していない？）

代替策として、下記方法があると考えられる。

1. Google Chromeの拡張機能のViewerを使用する方法。
2. Visual Studio Codeを使用する方法。

どちらも手間がかかるが、手間が少ないのは1だと考えられる。

## 1. Google Chromeの拡張機能のViewerを使用する方法
Dilingerでmdファイルを編集し、pdf出力・保存するときだけ、Google Chromeの拡張機能の"Markdown Viewer"を使用する。

"Markdown Viewer"は、ブラウザ（Chrome）上に.mdファイルを表示する機能であり、印刷機能でpdfとして出力する。

ただし、Chromeの拡張機能は、Desktop版でしか使用できないことに注意されたい（スマホではできない）。


[pdf出力例](watarukumagai-git/dillinger/alphadesign.pdf)


### 使用方法
- mdファイルの編集：Dillinger
- mdファイルの保存："SAVE TO"でDropboxに保存
- mdファイルのインポート："IMPORT FROM"でDropboxからインポート
- mdファイルのエクスポート："EXPORT TO"でローカルマシンにエクスポート
- pdf出力・保存："Markdown Viewer"でブラウザ上にmdファイルを表示し、印刷機能でpdf出力（その後、手動でDropboxにアップロード）

### 使用手順
#### 手順1
Google Chromeのブラウザを開く。
Chrome Web Storeから、[Markdown Viewer][url4]を拡張機能にインストールする。

   [url4]: <https://chrome.google.com/webstore/detail/markdown-viewer/ckkdlimhmcjmikdlpkmbgfkaikojcbjk>

#### 手順2
Chromeの拡張機能の設定ページ（chrome://extensions/）を開き、"Markdown Viewer"の詳細を開く。


"ファイルの URL へのアクセスを許可する"をONにする。

#### 手順3
ローカルの.mdファイルを、Chromeのブラウザ上にドラッグ&ドロップすると、内容が表示される。（これがMarkdown Viewerで表示している状態）

#### 手順4
Chromeの印刷機能（ショートカットキー：Ctrl＋P）で、送信先を"pdf"に設定し、ローカルに保存。

詳細手順は[Qiitaの記事][url6]を参照。

   [url6]: <https://qiita.com/takachan_coding/items/7a0978a70208e482aae9>

それ以降は手順3、4だけに従えば良い。

## 2. Visual Studio Codeを使用する方法
Dillingerを使うのを止めて、Visual Studio Code（VSコード）でmdファイルを編集し、VSコードの拡張機能"Markdown PDF"を使用してpdf出力する。

VSコードは、ITエンジニアが良く使うコードエディタである。

ただし、Dillingerはブラウザエディタなのでインストール不要だったが、VSコードはエディタソフトウェアなので別途インストールが必要。

また、社内マシンに標準以外のソフトウェアをインストールする際には、上司承認の上、部署の情報資産台帳に記入・管理する必要がある。（拒否されないと思うが、少し面倒）


### 使用方法
- mdファイルの編集：VSコード
- mdファイルの保存：ローカルに保存（その後、手動でDropboxにアップロード）
- pdf出力・保存："Markdown PDF"でpdf出力（その後、手動でDropboxにアップロード）

### 使用手順
詳細手順は[この記事][url7]を参照。

   [url7]: <https://anteku.jp/blog/develop/visual-studio-code%E3%81%AE%E6%8B%A1%E5%BC%B5%E6%A9%9F%E8%83%BD%E3%80%8Cmarkdown-pdf%E3%80%8D%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%A6%E3%81%BF%E3%82%88%E3%81%86/>


# 6. 注意事項
Dropboxは社内公認のクラウドサービスではないため、上の方法は裏技的な利用方法であることに注意されたい。

本来はY-GitHub、One Driveなど社内公認クラウドサービスを利用したいが、これらは申請や課金が必要になるし、
なぜかGithubは連携ができないため、今回はDropboxにした。

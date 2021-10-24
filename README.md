# Dillinger
markdownやDillingerに関する説明。

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


# markdownの記法
markdownでは、文字装飾、タイトル付け、箇条書き、表作成、画像挿入、URLのハイパーリンクなどが可能である。
[Markdown site][url2]や他のwikiなどを参照。

   [url2]: <https://backlog.com/ja/blog/how-to-write-markdown/>



# クラウドサービスとの連携
公式サイトでは、DillingerはDropbox、Bitbucket、Github、Google Drive、One Driveのクラウドサービスと連携できる、と書いてある。

しかし、下記の理由から、**Dropbox**と連携するのが一番利便性が良いと考えられる。
- 社内では、Google Drive（Googleアプリ系）が公式で利用できない（社内用gmail発行の申請が必要）
- 社内では、One Driveは社内公式用を課金制で利用できる
- Githubは、なぜか連携できなかった


## Dropboxと連携させた使い方
- mdファイルの編集：Dillinger
- pdf出力："PREVIEW AS"でブラウザ上に出力
- pdf保存："EXPORT AS"でローカルに保存
- mdファイルの保存："SAVE TO"でDropboxに保存
- mdファイルのインポート："IMPORT FROM"でDropboxからインポート

## ローカルのみの使い方
- mdファイルの編集：Dillinger
- pdf出力："PREVIEW AS"でブラウザ上に出力
- pdf保存："EXPORT AS"でローカルに保存
- mdファイルの保存："EXPORT AS"でローカルに保存
- mdファイルのインポート："IMPORT FROM"でローカルからインポート


# Dropboxとの連携方法
Dropboxとの連携方法を下記に示す。

## 手順1
[Dropbox][url3]でアカウントを作成する。

   [url3]: <https://www.dropbox.com>

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

後は手順3、4と同様。


# 注意事項
Dropboxは社内公認のクラウドサービスではないため、上の方法は裏技的な利用方法であることに注意されたい。

（本来はY-GitHubという社内用GitHubがあるが、これも申請や課金制なので必要になるし、なぜかGithubとの連携ができないため、今回は諦めた）

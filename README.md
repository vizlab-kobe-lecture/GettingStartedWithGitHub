# Getting started with GitHub

プロジェクト演習（データの可視化）では、開発するプログラムのソースコードを、GitHubを使ってバージョンを管理します。ここでは、演習で最低限必要と成るGitHubコマンドとその使い方を簡単に説明します。

## 1. アカウントの作成
まずは、GitHubアカウントを作成します。[GitHub](https://github.com/)のサイトにアクセスし、以下の手順でアカウントを作成してください。すでにアカウントを取得している人は、そのアカウントを使っても構いません。

1. 表示されるページに、ユーザ名、メールアドレス、パスワードを入力してください。
1. 正しく入力できれば「Sign up for GitHub」をクリックしてください。
1. プランの選択画面で、Freeプランが選択されていることを確認し「Finish sign up」をクリックしてください。
1. 登録したメールアドレスに確認メールが送られるので、受信後、メール内の「Verify email address」をクリックしてください。
1. 「Welcome to GitHub」というメールが届いたら登録完了です。

## 2. リポジトリの取得（clone）
vizlab-kobe-lectureに登録されているリポジトリを編集用にローカルPC環境にコピー（クローン）します。まず、取得するポジトリを格納するためのディレクトリを作成します。ここでは、ホームディレクトリ直下に「Project」という名前のディレクトリを作成し、そのディレクトリ内にリポジトリのコピーを作成することにします。

```
$ cd ~
$ mkdir Project
$ cd Project
```

次に、以下のようにgitのcloneコマンドを使って、テスト用リポジトリ（Test）を各自の環境にクローンしてください。以降、クローンしたリポジトリをローカルリポジトリと呼ぶことにします。そして、GitHubサーバ上にあるリポジトリをリモートリポジトリと呼ぶことにします。

```
$ git clone https://github.com/vizlab-kobe-lecture/Test.git
```

## 3. ファイルの作成
Testディレクトリ下にある年度名ディレクトリ（2016年度の場合「2016」）に移動し、以下の手順で学籍番号が名前のファイル（学籍番号が1234567tの場合、「1234567t.txt」）を作成してください。

```
$ cd Test/2016
$ echo "test message" > 1234567t.txt
```

## 4. ローカルリポジトリへのファイルの追加（add, commit）
新しく作成したファイルをGitHubで管理するために、リポジトリにそれを追加します。このとき、対象となるリポジトリは、リモートリポジトリではなくローカルリポジトリです。これには、追加するファイルの指定、その反映という２つの操作が必要なります。

まず、以下のようにgitのaddコマンドを使って、作成したファイル 1234567t.txt を指定します。

```
$ git add 1234567t.txt
```

次に、commitコマンドを使って、以下のようにして、指定されたファイルのローカルリポジトリへの追加作業を実施します。

```
$ git commit -m "first import"
```

この時点では、まだリモートリポジトリにはファイルは追加されていないことに注意してください。WebブラウザでGitHubの[Testリポジトリページ](https://github.com/vizlab-kobe-lecture/Test)にアクセスし、ファイルが追加されていないことを確認してください。

## 5. リモートリポジトリへの反映（push）
gitのcommitコマンドによってローカルリポジトリが更新されます。以下のようにgitのpushコマンドを使って、ローカルリポジトリの更新内容をリモートリポジトリへ反映することができます。必要に応じてユーザ名とパスワードを入力してください。

```
$ git push
```

この操作が完了すると、リモートリポジトリに作成したファイル 1234567t.txt が追加されます。先ほど同じようにして、WebブラウザでGitHubの[Testリポジトリページ](https://github.com/vizlab-kobe-lecture/Test)にアクセスし、ファイルが追加されていることを確認してください。

## 5. リモートリポジトリからの取り込み（pull）
リモートリポジトリを複数人で共有して開発を進める場合には、自分以外の誰かがリモートリポジトリの内容を更新する可能性があります。その場合は、以下のようにgitのpullコマンドを使って、その更新内容をローカルリポジトリに取り込むことができます。

```
$ git pull
```

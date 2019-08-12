# git-practice
GitHubを初めて使う方、日常生活で使わない方もいるので簡単なチュートリアルをしましょう。  
GitのことやGitHubのことは解説しないので検索して調べてください。  

## Gitをpcで使えるようにする
- GitHubのアカウントの作成
https://github.com で作成できます
- 自分のパソコンはgitが使えるか確認する
以下のコマンドでバージョンが表示されていたら使えます  
pcでコマンドプロンプトやターミナルで確認($のあとのコマンドをコマンドプロンプトやターミナルで
実行します)
```
$ git version
```
- もしgitコマンドが表示されないときはgitのインストールをします。  
https://git-scm.com/downloads でダウンロードができます。

- Gitの設定をする
ユーザー名とeメールをgitに登録します(GitHubに登録したやつと同じ)  
以下の"katapi"を各自の情報にしてください
```
$ git config --global user.name "katapi"
$ git config --global user.email katapi@example.com
```
- [推奨]ここでssh keyを発行してssh出来るようにしておくと開発の際にパスワードを入力する手間がなくなりますが省略しても構いません。github ssh keyとかで検索すると参考サイトがいろいろあると思います。

## リポジトリを自分のPCにcloneする
リポジトリは、作業しているファイルやディレクトリの状態ことです。自分のパソコン(デスクトップ)などにcloneします。  
コマンドプロンプトやターミナルでcloneする場所(デスクトップや任意の場所)に移動します。
```
$ git clone https://github.com/webiot-c/git-practice
```

コマンド操作でなくても(https://github.com/webiot-c/git-practice)からcloneできます。  
右上の「clone or download」からcloneできます。

## 開発をする
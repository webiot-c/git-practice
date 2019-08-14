# git-practice
GitHubを初めて使う方、日常生活で使わない方もいるので簡単なチュートリアルを書いてみました。  
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

コマンド操作でなくても(https://github.com/webiot-c/git-practice) からcloneできます。  
右上の「clone or download」からcloneできます。

## ブランチの作成
開発をする前にブランチを切る(切る == 作成)が必要です。ブランチは、作業の流れを分岐して記録するものです。何もしないとmasterブランチになっていると思います。以下のコマンドで確認してみましょう。

`#` はコメントです。
```
# 現在のブランチを確認する
$ git branch
```
コマンドで確認すると* master となっていると思います。ここから自分が開発するための"自分専用のブランチ"を作成します。
```
# masterブランチに移動(git branchでmasterになっていれば不要)
$ git checkout master

# 自分の名前のブランチを作成
$ git checkout -b katapi
```
自分のブランチに移動しているか確認します($ git branch)。移動していれば開発が出来ます。


## 開発をする
cloneしたリポジトリの中でいつもどおりソースコードを作成して開発をします。

今回は練習としてリポジトリ内にある`hello.txt`を編集してみます。

任意のエディタ(vscodeとかvimとか)で`hello.txt`を開きます。とりあえず自分の名前を追記しておきましょう。

保存してエディタを閉じます。次にGitHubにpushします。

## GitHubにcommit/push
自分が編集した内容をGitHubに投げて共有します。するとチームの人と変更履歴を共有することが出来ます。

```
# 最初にインデックスの確認をする(念の為ブランチの確認も)
$ git status
$ git branch
# ブランチはmasterになっていないことを確認してください

# gitのインデックスに追加(リポジトリにコミットする準備)
$ git add .

#コミットする(add new fileはコメントなので任意のコメントで)
$ git commit -m "add new file"

# pushする
$ git push origin ブランチ名(katapiとか)
```
pushまで行うと(https://github.com/webiot-c/git-practice) に自分が修正・変更した内容が反映されていると思います。

**注意**:
masterブランチは、変更・編集しない  
masterブランチは、メインのブランチです。pushするときも`$ git push origin master`しないよう気をつけてください。  
(複数人で開発を行う際の場合です)

## masterブランチにmergeする
自分で作成したブランチをmasterブランチにmerge(結合)する作業をします。  
GitHubを見ると「Compare & pull request」ボタンがあります。そこからpull requestを作成します。タイトルは、追加したものや編集内容を記述します。  
「Create pull request」で完了です。  
「merge pull request」を押してmerge完了です。  
グループの人にレビューしてもらいたいときは、Create pull requestまでで大丈夫です。右上のReviewersでkatapiでも指定しておけばレビューします。


簡単にgitを用いた開発フローの紹介をしました。基本的には、

1. 開発をする
1. git add
1. git commit -m ""
1. git push 

という流れです。

## 参考
- GitHub Guide(公式チュートリアル)  
https://guides.github.com/activities/hello-world/

- サルでもわかるGit入門  
https://backlog.com/ja/git-tutorial/
# gitを用いた開発の流れ
## 使用するブランチモデル
masterブランチを最新のものにし、機能の名前を付けたブランチを切って開発

その機能が完全に完成したブランチをpull requestし、コードレビューを終えたらmasterブランチにマージする


### 参考


[git flowとgithub flowとは？その違いは？](https://qiita.com/mint__/items/bfc58589b5b1e0a1856a)


[GitHub Flow 図解](https://qiita.com/tbpgr/items/4ff76ef35c4ff0ec8314)


## 初期設定
1. 作業場所の作成
~~~
$ git clone ここにリポジトリのパス(URL)
例: git clone https://github.com/zamarin-dev/learning-git.git
~~~
## 開発（機能追加）
2. GitHubに上がっているソースコードと同一のものにする
~~~
$ git pull
~~~
3. masterブランチにいることを確認する。もしmasterでないならmasterブランチに移動する
~~~
$ git branch
$ git checkout master
~~~
4. 新しいブランチを作成して移動する。機能の名前は特に指定はなし。
~~~
$ git checkout -b (機能の名前)
例: $ git checkout -b modify_image_func
~~~
5. ソースコードの修正（機能の追加）
6. ブランチに追加（インデックスにステージ）
~~~
// ファイルを指定してブランチに追加
$ git add file名
例: $ git add readme.txt

// 全てのディレクトリをブランチに追加
$ git add .
~~~
7. ステージされたものをコミットする（どんな変更かを記述する）
~~~
$ git commit -m "ここに修正内容を書く"
例: $ git commit -m "強制終了するバグを修正"
~~~
8. 5~7を繰り返す
9. 自分の変更をリモートホスト（GitHubにあがっているもの）へ反映
~~~
$ git push origin ここにブランチ名
例: $ git push origin modify_image_func
~~~
10. GitHubのリポジトリのサイトからPull Requestを作成

# MkDocs

[公式サイト](http://mkdocs.org)

Static Site Generator（静的サイト作成ツール）の１つ。サイトの枠組みを簡単に作ることができる。本文にマークダウン方式を使える。
[参考](http://matome.naver.jp/odai/2138951779950545401)

## 環境

* Python
* pip

今回はCloud9（仮想サーバー）を使用。

## 使ってみた。

        公式サイトを見ながら使ってみた。

1 pipを使ってmkdocsをインストール。（先頭に「sudo」が必要らしい）

        sudo pip install mkdocs
    
2 mkdocsのフォルダを作成。ディレクトリを変更する。

        mkdocs new フォルダ名
        cd フォルダ名
    
3 サイトをランする。（Cloud9でランするには-a以下が必要）

        mkdocs serve -a 0.0.0.0:8080
    
4 http://0.0.0.0:8080をクリックすることでサイトをブラウザで表示できる。

5 サイトのランは「Ctrl + C」で停止可能

6 サイト名を変更する。

        mkdocs.yml内のsite_name: サイト名
    
7 新しいページを加える。今回は外部のコンテンツをそのまま加えてみる。[curlについて](https://hydrocul.github.io/wiki/commands/curl.html)

        curl 'jaspervdj.be/lorem-markdownum/markdown.txt' > docs/about.md
    
8 ヘッダーの変更。ただ、今の段階ではなくても勝手にやってくれている。

        mkdocs.yml内に
            pages:
            - Home: index.md
            - About: about.md
                            
9 レイアウトの変更。

        mkdocs.yml内にtheme: readthedocs
    
10 markdownをhtmlに。

        mkdocs build

11 GitHubページにアップロード。

        mkdocs gh-deploy

0 ファイルツリー内で新しいファイルを作る分には問題なかったが、別階級のファイルをコピペした時はうまく動かなかった。


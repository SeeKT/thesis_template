# Thesis template
TeXで卒論や修論などを作るときの備忘録です．他にも，TeXで長めの資料を作るときにも活用できるかと思います．

### documentclassについて
`jsbook` を使っています．そのため，コンパイル時は `platex` で行うと良いと思います．

### ディレクトリ構成とコンパイルの方法
以下のようなディレクトリ構成にしています．
```
|- bib/: bibtexするやつ
|   |- hogehoge.bib
|
|- fig/: 図を入れるディレクトリ
|   |- Chapter3/: 各章ごとに分けたほうが見やすいと思う
|
|- main/: main.tex のディレクトリ
|
|- tex/: main.texにinputするTeXソースのディレクトリ
|   |- preamble_thesis.tex: プリアンブルをまとめたTeXファイル
|   |- その他inputするTeXソース
```

コンパイルは，`main/` の `main.tex` をコンパイルします．`.latexmkrc` を作れば楽です．

```
platex main.tex
pbibtex main
platex main.tex
platex main.tex
platex main.tex
dvipdfmx main.dvi
```

#### このようなディレクトリ構成にするメリット
- 1つのTeXソースの文章量が比較的少なくなる．
- 図がどこにあるか見やすい．
- 参考文献の管理が楽．

### その他
PDFファイルの謝辞の部分の目次のページ番号がおかしいのは直せなかったです．使う人は何とかしてください (丸投げ)．

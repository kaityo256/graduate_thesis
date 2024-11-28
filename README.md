# 卒業論文テンプレート

## 概要

慶應義塾大学理工学部物理情報工学科の卒業論文のための**非公式**テンプレートです。提出にあたっては実際の指示に従ってください。

## 内容

* `thesis.tex` 卒論本体のLaTeXファイル。
* `abstract.docx` 要旨提出用のWordファイル。
* `cover.pptx` 製本を依頼する際の表紙データ。
    * 印刷して「上製本で」と指定して生協に出すときれいに製本をしてくれる。製本しない場合は不要。

## 使い方

HTTPSでクローンして、リポジトリを初期化し、新たにリポジトリを作る。

```sh
cd
cd github
git clone https://github.com/kaityo256/graduate_thesis.git
cd graduate_thesis
rm -rf .git
git init
git add .
git commit -m ":tada: initial commit"
```

さらにGitHub等でプライベートリポジトリとして管理することを強く推奨する。

## コンパイル方法

TeXLiveをインストールし、LaTeXでコンパイルすればよいが、`latexmk`によるコンパイルを推奨する。`.latexmkrc`は、例えば以下のようにすれば良い。

```sh
#!/usr/bin/env perl

$latex = 'platex -synctex=1 -interaction=nonstopmode %O %S';
$bibtex = 'pbibtex %O %B';
$pdf_mode = 3;
$dvipdf = 'dvipdfmx %O -o %D %S'
```

正しくインストールされていれば、

```sh
latexmk
```

を実行することで`thesis.pdf`が作成される。

## ライセンス

CC-BY

pymd2re
===

![Software Version](http://img.shields.io/badge/Version-v0.1.0-green.svg?style=flat)
![Python Version](http://img.shields.io/badge/Python-3.6-blue.svg?style=flat)
[![MIT License](http://img.shields.io/badge/license-MIT-blue.svg?style=flat)](LICENSE)

## 概要
MarkdownファイルをRe:VIEWファイルに変換するスクリプト

## バージョン
v0.1.0

## 動作環境
- Python 3.6以上
- 標準ライブラリ以外の依存ライブラリは無し

## ライセンス
MIT License

## 使用方法
`pymd2re.py` を実行する。

    usage: pymd2re.py [-h] input_path output_path
    
    Convert Markdown file to Re:VIEW file.
    
    positional arguments:
      input_path     Input File Path. (Markdown file)
      output_path    Output File Path. (Re:VIEW file)
    
    optional arguments:
      -h, --help     show this help message and exit

## サンプル
- `pymd2re.py` による出力結果
    - 入力ファイル：[sample_input.md](sample/sample_input.md)
    - 出力ファイル：[sample_output.re](sample/sample_output.re)
    - 変換時の警告：[warning_stdout.txt](sample/warning_stdout.txt)
- `debug.py` による中間データの可視化
    - 入力ファイル：[sample_input.md](sample/sample_input.md)
    - 出力内容：[debug_stdout.txt](sample/debug_stdout.txt)

## 制限事項
- 同一行に複数種類のブロックが存在するケースは不可
    - 行の途中から複数行コメントが始まるなど
    - 同一行に複数種類のインライン要素は許可
- 以下には未対応（順次対応したい）。
    - インライン要素のネスト（リンクの中でボールドなど）
    - コードブロックの言語名の取得（無視して処理を継続）
    - 外部参照リンク（あらかじめリンクを定義して複数回記述する書き方のこと）
    - 文書内の見出しへのリンク（書いた通りに出力されてしまう）
    - 表内の列のアライメント指定の取得（無視して処理を継続）
    - チェックリストのチェックON/OFFの取得（無視して処理を継続）
    - マークダウン記号のエスケープ（エスケープと認識しない）

## メモ
- 構文解析は正規表現の力技で実装した。
- 文書構造を中間表現で保持する方式のため、レンダラを用意すればRe:VIEW以外のフォーマットへの出力も可能になるはず。

## TODO
- Re:VIEW Starter 拡張を使用するオプションに対応する。

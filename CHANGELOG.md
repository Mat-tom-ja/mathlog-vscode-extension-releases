# Change Log

All notable changes to the "mathlog-vscode-extension" extension will be documented in this file.

Check [Keep a Changelog](http://keepachangelog.com/) for recommendations on how to structure this file.

## [0.0.3] - 2026-09-22

- ファイルアイコンと拡張機能本体のアイコンを、緑とピンクの「C」ロゴに変更した。
- アイコンは`npm run icons:generate`で参照画像`images/icon/mathlog-icon-source.png`から生成するようにした。
- リリースビルドをGitHubのプレリリースとして添付するようにした（`npm run release:publish`）。

## [0.0.2] - 2026-09-22

- 難読化済みVSIXのビルド手順を追加した。
- `.mathlogmd`と`.mathlogmacros`のファイルアイコンを追加した。
- Marketplace向けREADMEを英語化した。

## [Unreleased]

## [0.0.7] - 2026-09-23

### Added

- `mathlog.formatting.characterReplacements`を追加し、`、`→`,`のような任意の文字置換を設定できるようにした。

## [0.0.6] - 2026-09-23

### Added

- プレビューで`<br>`を改行として通すようにした（`</br>`は安全のため文字列のまま）。

## [0.0.5] - 2026-09-23

### Added

- Markdown表の列を、行長にかかわらず常にPrettierで整列するようにした（従来は80文字を超える表だけ整列していた）。

## [0.0.4] - 2026-09-23

- 初回公開へ向けた準備中。

### Added

- `.mathlogmacros`（言語`mathlog-macros`）へ整形とセマンティックハイライトを追加した。本文を数式として整形し、定義コマンド・マクロ・引数・コメントをテーマの色で着色する（プレビューは対象外）。
- 箇条書き・引用・表・水平線・リンク・画像・HTML・コードの色分けを追加し、`mathlog.highlighting.disabledDecorations`と`mathlog.highlighting.insideFormalBlocks`でカテゴリ単位に無効化できるようにした。
- 既定テーマが色を持たない水平線・表の区切り・宣言ラベルへ、拡張の既定色（薄いグレー）を与えるようにした。
- 文法が出力する全スコープが既定テーマか拡張の既定色で着色されることを確認するテストを追加した。
- 色分けを確認する`examples/color-samples.mathlogmd`を追加した。
- プレビューでワークスペース内の画像記法を表示できるようにした。文書からの相対パスを優先し、許可した範囲の外と外部URLは読み込まない。

### Changed

- 文字装飾（`**太字**`・`*斜体*`・`~~取消線~~`）はエディタで色を付けない既定に変更した（プレビューでは従来どおり反映する）。
- 形式ブロック内のタブ字下げ行も、Mathlog本体と同じくコードとして色分けするようにした。
- プレビューで`<span style="color: ...">`のような`span`・`div`の`style`の`color`を反映するようにした（他の宣言・属性は安全のため落とす）。

### Fixed

- MathJax起動後にプレビューの更新メッセージで例外が発生し、編集がプレビューへ反映されない不具合を修正した。
- プレビューを開いたまま追加したマクロが反映されない不具合を修正した（削除は開き直しまで残る）。
- VS Code統合テストの既定タイムアウトでは環境によって失敗するテストに対して、余裕のあるタイムアウトを設定した。

### Documentation

- READMEを利用者向け（機能・インストール・使い方・設定・制限）に書き直した。
- 仕様を`docs/spec/`（フォーマット・ハイライト・プレビュー・診断・マクロと参考文献）と`docs/dev/`（アーキテクチャ・テスト・リリース）へ整理した。

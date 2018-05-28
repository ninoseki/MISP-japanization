# MISP Japanization

This is a repo for the japananization (adding Japanese language support) of [MISP](https://github.com/MISP/MISP).

![img](http://i0.kym-cdn.com/entries/icons/original/000/022/336/FBIonicle.png "img")

## How to contirubte

- There is an official Crowdin project for i18n. You can commit a translation via the Crowdin project.
  - https://crowdin.com/project/misp
- ref.
  - [脆弱性診断ツール「OWASP ZAP」の翻訳サイト「Crowdin.net」の使い方](https://qiita.com/nightyknite/items/402e639b9d64d8f8eca5)

## How to verify the Web UI

- copy `/MISP/app/Locale/default.pot` to `/MISP/app/Locale/jpn/LC_MESSAGES/default.po` and then edit it.
- Note: if the contents of .po file doesn't reflect to the Web UI, you should clear out `/MISP/app/tmp/cache/persistent` directory.

- You can download the latest .po file via https://crowdin.com/project/misp/ja#.
  - ![Imgur](https://i.imgur.com/lyw2YLy.png)

## Translation rules

Note: The rules are forked from [akka-ja/akka-doc-ja](https://github.com/akka-ja/akka-doc-ja).

### 全角文字と半角文字

英数字と記号は原則として半角で記述してください。

- 数字: `0` から `9`
- 小括弧: `(` と `)`
- 感嘆符: `!`
- 疑問符: `?`

カタカナ、句読点は全角で記述してください。

- 句点: `、`

### スペース

可読性向上のため、原則として全角文字と半角文字の間に半角スペースをひとつ挿入してください。ただし、以下は例外とします。

- 全角句読点と (reStructuredText 記法ではない) 半角英数字が続く場合
- 半角開き小括弧 `(` の直後に全角文字が続く場合
- 全角文字の直後に半角閉じ小括弧 `)` が続く場合

以下の例の場合、最初の `Java` の前、`Linux` の前、`(` の後、`)` の前、そして `Windows` の前に半角スペースを挿入する必要はありません。

> MacOS を使っているなら、Java は導入済みです。また、Linux を使っているなら Sun JDK か OpenJDK のいずれかを使えるか確認してください (また gcj があるかどうかも確認してください。これは多くの Linux のディストリビューションで標準の Java コマンドです) 。Windows を使っている場合は最新の JDK をダウンロードしてインストールしてください。

### 訳語の統一

固有名詞や専門的な用語を無理に翻訳する必要はありません。

表記揺れなどで迷った場合は、Google や英辞郎 on the WEB の検索結果を目安にしてください。

- 例: repository
  - リポジトリ: 約 2,030,000 件
  - レポジトリ: 約 363,000 件
  - [repositoryの意味・用例｜英辞郎 on the WEB：アルク](http://eow.alc.co.jp/search?q=repository)

### 意訳、訳註について

原則として、原文に存在しない情報は付け加えないでください。

以下のような場合は、意訳を検討するとよいでしょう。

- 英語特有の表現を含む場合
  - 例: `out of the box` => 直訳: `箱から取り出して (そのまま) `  、意訳: `特別な設定をしなくても`

  - 例: 英語のジョーク、映画の台詞の引用など

その他、訳語は存在するものの、日本語として馴染みがなく分かりづらい場合は、適宜、意訳または訳註を行ってください。

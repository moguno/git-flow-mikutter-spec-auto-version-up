これなん？
======================================

mikutterのプラグインを書くのってお手軽で超エキサイティングですよね！  
でも、プラグインのリリースの度にspecファイルのバージョンを更新するのはちょっと面倒。  
てか忘れますよね普通に。

そんな事故が怖くてspecファイル添付に尻込みしている貴方（is 俺）に朗報です！

git-flowのrelease start時に、specのversionにキーワードを自動で埋め込みます。


使い方
======================================
ダウンロードしたpost-checkoutに実行パーミッションを付けて.git/hook/に格納してください。  
後はいつも通りgit flow release startすればOKっす。

<pre>
$ git flow release start 0.9.9-teokure
Switched to a new branch 'release/0.9.9-teokure'
specファイルのバージョンを0.9.9-teokureに更新しときました。

・・・

$ cat spec
---
slug: :rss
depends:
  mikutter: 0.2.2.1264
  plugin:
  - settings
  - gui
  - gtk
version: 0.9.9-teokure　　　　←これ！！
author: moguno
name: mikutter RSS TL
description: ホームタイムラインにRSSフィードを混ぜ込みます。
</pre>

あ、シェバング（1行目のアレ）はMacPortsで入れたRuby1.9に特化しているので、適宜書き換えてください。

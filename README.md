
# flutter_listView

A first Flutter project.

## Getting Started

https://codelabs.developers.google.com/codelabs/first-flutter-app-pt1#1

公式チュートリアル:ListViewを作成（lib/main.dart）


## [brew install flutter] Flutter 環境構築

Flutterの環境構築する際に色々と更新などが必要となりましたので、
どのように対処したのかを残しておきます。

1. brew install flutter
    Homebrewで[flutter]をインストールできるのですが、その前に更新等が必要となりました。

2. brew update
    Homebrewのupdateが必要との事で上記コマンドを実行しましたが、エラー。

```
Error:
  homebrew-core is a shallow clone.
To `brew update`, first run:
  git -C /usr/local/Homebrew/Library/Taps/homebrew/homebrew-core fetch --unshallow
```
	
# 解決方法
メッセージ内の git コマンドを実行します。
```
git -C /usr/local/Homebrew/Library/Taps/homebrew/homebrew-core fetch --unshallow
```

いよいよ、[brew install flutter]をしたのですが、次は[cocoaPods　upgrade]しろというような警告が・・・・


[sudo gem update]でgemを更新したが、またしてもエラー。
```
ERROR:  While executing gem ... (Gem::FilePermissionError)
    You don't have write permissions for the /usr/bin directory.
```

# 解決方法
[sudo gem update -n /usr/local/bin bundler]
パスを変更することでエラーを解決。
同様に、[sudo gem update cocoapods -n /usr/local/bin bundler]することで、cocoaPodsの更新も完了。

最後、[flutter doctor]コマンドで、無事に[No issues found!]となりました。


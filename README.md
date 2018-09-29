# QiitaNote

## 目的・コンセプト

Qiitaのストックを管理する。振り返りやすくする。

## 発生した問題

- 特定の条件下において、OAuth認証画面が開けない
  - requests.get(oauth-page-url)が原因
  - 入力に渡したURLとresutlsObj.urlが異なっていた
  - 直にリンクを貼る、リンクを文字列として処理することで解決した
- thisの混同
  - VueComponents > getLoginURL > this
  - getLoginURL > function > this
  - getLoginURL > this　を変数vmに格納してから、function > vm.XXX
  - アロー(=>)を使うことでも可能
- 「nullではない」の比較には、「!==」を使う
  - サーバから返されたJSONのキーによって表示を切り替える
  - 具体例）ログイン済みなら、ログインリンクを表示しない
  - !=では、検知できないため、!==を使用する

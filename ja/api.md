API
=====

core コンポーネント
-----

###Action

####saveSession


#####パラメータ1: apikey\*

#####パラメータ2: name\*

- セッションを保存するディレクトリへの絶対パス + 保存するファイルの接頭文字列
- （例）`/Users/yuki/tmp/zap_session_save_test/foo` を渡すと、`/Users/yuki/tmp/zap_session_save_test/` 内に、以下のファイルとディレクトリが生成される。
    - `foo.session`
    - `foo.session.data`
    - `foo.session.lck`
    - `foo.session.log`
    - `foo.session.properties`
    - `foo.session.script`
    - `foo.session.tmp/`

#####パラメータ3: overwrite

- `"true"` or `"false"`

#####戻り値 [JSON]:

- 成功時：`{"Result":"OK"}`


authentication コンポーネント
-----

###Action

####setAuthenticationMethod


#####パラメータ1: apikey\*
#####パラメータ2: contextId\*
#####パラメータ3: authMethodName\*
#####パラメータ4: authMethodConfigParams
- key1=value1&key2=value2&... の形式で複数のパラメータとその値をセットする。
- Form-based Authentication の場合は、以下のパラメータをひとまとめにしてこのフィールドにセットする。
    - `loginUrl`
    - `loginRequestData`
        - これはPOSTリクエストでで渡すデータである。
        - ユーザ名の文字列部分は、`"{%username%}"`、パスワードの文字列部分は、`"{%password%}"` にしないといけない。
        - CSRF対策トークンも渡した方がよさそう。
- このあたりのことが定義されているファイル
    - `org.zaproxy.zap.authentication.FormBasedAuthenticationMethodType`



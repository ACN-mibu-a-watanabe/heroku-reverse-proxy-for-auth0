# Auth0カスタムドメインSSL接続用のリバースプロキシ

nginxをHeroku上に構築し、Auth0のカスタムドメインのためのリバースプロキシを起動します。

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

## どうして必要なのか

Auth0には、カスタムドメインを設定することができますが、直接自己管理している証明書をAuth0に設定させることができません。

参考）https://auth0.com/docs/custom-domains/self-managed-certificates

そこでHeroku上にリバースプロキシを構築し、クライアントとHeroku間を自己管理証明書による接続、HerokuとAuth0間をAuth0管理の証明書による接続を行わせることで、問題を解決させます。

クライアントとHeroku間の証明書の設定については、リファレンスを参照ください。


## インストール

[Deploy to Heroku](https://heroku.com/deploy) ボタンを使って自分のHerokuアカウントにアプリケーションをデプロイして下さい。

## カスタム設定値

- AUTH0_ORIGIN_DOMAIN_NAME: カスタムドメインの設定プロセス中にAuth0ダッシュボードから取得したOrigin Domain Nameの値を設定します。
- AUTH0_CUSTOM_HEADER_API_KEY: カスタムドメインの設定プロセス中にAuth0ダッシュボードから取得したOrigin Custom Headersのキーを設定します。
- AUTH0_CUSTOM_HEADER_API_VALUE: カスタムドメインの設定プロセス中にAuth0ダッシュボードから取得したOrigin Custom Headersのバリューを設定します。

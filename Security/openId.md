# OpenID Connectとは
OpenID Connectは、IDトークンを発行する仕組みのこと。
クライアントアプリから、利用したいサービス(さきサービスAと呼ぶ）に認証した場合に、認証用のサーバー（OpenIDプロバイダー）から認証してもらうことで、サービスAにアクセスできるようにするやり方。


## 登場人物
1. ユーザー
2. クライアントアプリ
3. OpenID プロバイダー
4. アクセスしたサービス

## フロー
1. クライアントアプリがOpenIDプロバイダーに対し、IDのトークン発行を依頼する
2. OpenIDプロバイダーは、ユーザーに対し、本人確認情報の提示を求める。
3. ユーザーがトークンの発行を了承し、本人確認情報をOpenIDプロバイダーにわたす。
4. OpenIDプロバイダーがクライアントアプリに対して、IDトークンを渡す。


## IDトークンとアクセストークンの違い



## OAuth 2.0 / OpenID Connect の使いみち
- [OAuth 2.0 / OpenID Connect の使いみち](https://qiita.com/wadahiro/items/ad36c7932c6627149873)
- [OpenID Connectユースケース、OAuth 2.0の違い・共通点まとめ](https://www.buildinsider.net/enterprise/openid/connect)

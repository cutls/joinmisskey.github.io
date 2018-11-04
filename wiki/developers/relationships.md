---
title: 他のサービスとの連携を設定する
description: Twiitter及びGitHubでの認証を利用することができます。これには管理者側での設定が必要です。
layout: wiki
---
## Twitter
噂に入っているかもしれませんが、Twitterアプリの作成には使用用途を記入し審査を受ける必要があります。  
審査には数日かかるようです。

### 1. Twitterアカウントを作成
Twitterアカウントを持っていない場合、作成する必要があります。

### 2. Developer Accountとして認証し、アプリを作成
[この記事(A)](https://masatoshihanai.com/php-twitter-bot-01/#Twitter_APIdeveloper_account)や[この記事(B)](https://www.torikun.com/entry/twitter-developer-api#Twitter-Developer%E3%82%B5%E3%82%A4%E3%83%88%E3%81%AB%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9)を参考にDeveloper Accountとして認証し、アプリを作成してください。  
(記事AはDeveloper Accountの認証まで、記事Bはアプリの作成まで解説されています)

アプリのコールバックURLは`https://(your-misskey-instance)/api/tw/cb`というように指定します((your-misskey-instance)は自分のインスタンスのドメインに置き換えます。)

### 3. キーをconfigに記入
`/.config/example.yaml`の144行目付近のtwitterセクションを参考に、`consumer_id`と`consumer_secret`を入力します。

### 4. Misskeyを再起動
Misskeyを再起動したら完了です。自分のアカウントを認証してみてください。(`設定` > `プロフィール`)

## GitHub
GitHubの認証の設定はとても簡単です。

### 1. GitHubアカウントを作成
GitHubアカウントを持っていない場合、作成する必要があります。

### 2. OAuth Appを作成
右上の(自分のアイコンの)部分をクリックして`メニュー`を表示 > `Setting` > 左側のメニューから`Developer Settings` > `new OAuth App`

Authorization callback URLは`https://(your-misskey-instance)/api/gh/cb`というように指定します((your-misskey-instance)は自分のインスタンスのドメインに置き換えます。)

### 3. キーをconfigに記入
`/.config/example.yaml`の150行目付近のgithubセクションを参考に、`client_id`と`client_secret`を入力します。

### 4. Misskeyを再起動
Misskeyを再起動したら完了です。自分のアカウントを認証してみてください。(`設定` > `プロフィール`)
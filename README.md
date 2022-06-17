# laravel-default
このリポジトリにはLaravelの初期設定済みのソースが置いてあります。<br>Laravelでサービスを開始する際にクローンしてお使いください。

## 構成・バージョン
- Laravel Framework 9.9.0
- MySQL 8.0.28
- Redis 6.2.6
- MailHog 1.0.1
- Vue.js 2.6.14

### １．クローンする
```
git clone https://github.com/m-yamaguchi5811/laravel-default.git
```

### ２．アプリ（Laravel）のサービス名に変更する
以下のファイルの「laravel-app」の部分をサービス名に修正する。<br>
（修正しなくて使用できますので、取り敢えず動かしたい場合はそのままで大丈夫です。）
#### docker-compose.yml
```
4行目
laravel-app:
```

#### .env
```
7行目
APP_SERVICE="laravel-app"
```

### 3．Sailコマンドの設定
以下のコマンドを実行してSailコマンドを使いやすくする。
```
alias sail='[ -f sail ] && bash sail || bash vendor/bin/sail'
```

### 4．コンテナの作成と起動
```
sail up
```

### 5．必要なパッケージをインストール
```
sail composer install
```

### 6．ブラウザで確認する
以下のURLにアクセスする。<br>
http://localhost/
<br>
<br>

## 補足．Sailコマンド
### コンテナ作成・起動
```
sail up
```
### コンテナ作成・起動（バックグラウンド）
正常に動いている場合こちらをおすすめします。
```
sail up -d
```
### コンテナ停止
```
sail stop
```
### コンテナ一覧（起動しているコンテナのみ）
```
sail ps
```
### アプリ（Laravel）のコンテナに接続
```
sail shell
```
### MySQLに接続
```
sail mysql
```
### Redisに接続
```
sail redis
```
### artisanコマンド
`sail artisan` のみ実行すると、<b>help</b> が表示されます。
```
sail artisan [command]
```
### PHPUnit実行
```
sail test
```
### Composer
```
sail composer []
```
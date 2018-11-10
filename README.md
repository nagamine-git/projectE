# Railsアプリデモ

## Local環境での使い方
```bash
# 構築
docker-compose build
# bundle install
docker-compose run --rm web bundle install
# 起動
docker-compose up
# 停止
docker-compose down
# マイグレーション
docker-compose run --rm web rake db:migrate
# SQLへのつなぎ方
docker-compose run --rm web rails db
```

## デプロイ
```bash
# 準備
npm install -g heroku
# ログイン
heroku login
# リモートに接続
heroku git:remote -a efg-forum
# push
git push heroku master
# migrate
heroku run rake db:migrate
```

## ログ監視方法
```bash
heroku logs -t
```

## DBへのアクセス方法
```bash
# ローカルにpsqlを入れる
brew install postgresql
# heroku上のpsqlを見る
heroku pg:psql
```
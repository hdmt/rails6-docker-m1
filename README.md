# 実行環境

docker desktop 4.5.0
mac OS 12.2.1 (M1チップ)

# 構築手順

空ファイル作成

```
touch {Dockerfile,docker-compose.yml,Gemfile,Gemfile.lock,entrypoint.sh}
```

Dockerfile　編集

https://github.com/hdmt/rails6-docker-m1/blob/main/Dockerfile

docker-compose.yml　編集

https://github.com/hdmt/rails6-docker-m1/blob/main/docker-compose.yml

Gemfile

https://github.com/hdmt/rails6-docker-m1/blob/main/Gemfile

entrypoint.sh

https://github.com/hdmt/rails6-docker-m1/blob/main/entrypoint.sh

ビルド実行

```
docker-compose build
```

rails new 実行

```
docker-compose run web rails new . --force --no-deps --database=mysql
```

config/database.yml　編集

https://github.com/hdmt/rails6-docker-m1/blob/main/config/database.yml

dbの作成

```
docker-compose run web rails db:create
```

webpacker install

```
docker-compose run web rails webpacker:install
```

起動

```
docker-compose up
```

`http://0.0.0.0:3000/` でアクセス確認

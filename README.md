# 開発環境を構築

## ローカル作業準備

リポジトリのクローン

```
git clone {URL}
```

作業ディレクトリへの移動

```
cd picshare-database
```

## データベース環境の構築

コンテナを起動

```
docker-compose up -d
```

### 初期設定

データベースを作成

```
docker-compose exec db mysql -u root
Enter password:password

mysql> CREATE SCHEMA IF NOT EXISTS `picshare` DEFAULT CHARACTER SET utf8mb4;
```

ユーザを作成

```
docker-compose exec db mysql -u root
Enter password:password

mysql> CREATE USER 'picshare'@'%' IDENTIFIED BY 'password';
mysql> GRANT SELECT, INSERT, UPDATE, DELETE ON *.* TO 'picshare'@'%' WITH GRANT OPTION;
```

## マイグレーション

TODO: マイグレーションするときに。

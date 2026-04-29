# 2024BeginnerTrainingDataBaseBasic
24新卒技術研修_データベース研修_DB設計基礎

# Database Basic Training Log

MIXI GROUP が公開しているデータベース基礎研修教材を使用し、  
ローカル環境で各種データベースの基本操作を実践した学習記録です。

## 元教材

- https://github.com/mixigroup/2024BeginnerTrainingDataBaseBasic

## 学習目的

- RDB / NoSQL / インメモリDB の基本的な違いを理解する
- Docker Compose を使って各DBをローカルで起動する
- 各DBの基本的なCRUD操作を実行する
- SQLインジェクションの基本的な仕組みと対策を理解する

## 実施内容

| 技術 | 学習内容 | 状況 |
|---|---|---|
| MySQL | テーブル作成、INSERT、SELECT、JOIN、UPDATE、DELETE、ROLLBACK | 完了 |
| DynamoDB Local | put-item、scan、get-item、GSI、update-item、delete-table | 完了 |
| MongoDB | insertMany、find、ネスト検索、配列検索、updateMany、deleteMany | 完了 |
| Cassandra | keyspace作成、テーブル作成、CSVロード、SELECT、ALLOW FILTERING、UPDATE、DROP | 完了 |
| Redis | SET / GET、TTL、INCR、List、Set、Hash、FLUSHALL | 完了 |
| Juice Shop | Docker起動、SQLインジェクション演習、スコアボード確認 | 完了 |

## 学習メモ

### MySQL

リレーショナルデータベースの基本操作を確認しました。  
テーブル作成、データ投入、条件検索、JOIN、更新、削除、rollback の挙動を実行しました。

### DynamoDB Local

Key-Value / Document型DBとして、プライマリキーによる取得、scan、GSIを使った検索を確認しました。  
DynamoDBでは、事前にアクセスパターンを考えてキー設計する重要性を学びました。

### MongoDB

JSONに近いドキュメント形式でデータを保存し、ネストした項目や配列に対する検索を確認しました。  
環境上、教材のMongoDBイメージではコンテナが終了したため、学習用に `mongo:7` へ変更して実行しました。

### Cassandra

ワイドカラム型DBとして、keyspace、テーブル作成、CSVロード、Primary Keyを使った検索を実行しました。  
Cassandraでは、Primary Key設計が検索方法に強く影響することを確認しました。

### Redis

インメモリKey-Valueストアとして、文字列、TTL、カウンター、リスト、セット、ハッシュを操作しました。  
キャッシュ、セッション管理、カウンター、キュー用途に向いていることを確認しました。

### Juice Shop

脆弱性学習用アプリをDockerで起動し、SQLインジェクションによるログイン回避の仕組みを確認しました。  
ユーザー入力をSQL文字列へ直接連結する危険性と、プリペアドステートメントの重要性を学びました。

## 使用環境

- Windows 11
- PowerShell
- Docker Desktop
- Docker Compose
- Git / GitHub

## 備考

このリポジトリは、公開教材を用いた個人学習記録です。  
元教材の著作権・ライセンスは、元リポジトリに従います。


## Git クローン

```bash
$ git clone git@github.com:mixigroup/2024BeginnerTrainingDataBaseBasic.git

$ cd 2024BeginnerTrainingDataBaseBasic
$ export WORKDIR=$(pwd)

# WORKDIR 変数が設定されていることを確認
$ echo $WORKDIR
/Users/hoge/hoge/2024BeginnerTrainingDataBaseBasic
```


## 4章 演習

### その１ テーブル構造の比較

リレーショナルデータベース、キーバリューストア、ドキュメント指向データベースの違いを感じてもらいます。  
ほぼ同じデータをそれぞれに入れて基本操作をしながら、3つのデータベースを比較してみましょう。    
製品は MySQL、DynamoDB Local、MongoDB です。  

1. [MySQL](./mysql/README.md)
2. [DynamoDB Local](./dynamodb/README.md)
3. [MongoDB](./mongodb/README.md)

### その2 ワイドカラムの操作

ワイドカラムの基本操作を学びます。  
製品は Cassandra です。  

4. [Cassandra](./cassandra/README.md)

ワイドカラムは専門的な知識が必要なデータベースです。今回は基本的な操作のみとなっています。  
もしも配属先でワイドカラムを使うようなことがあれば、十分な学習が必要だと想像します。  

### その3 インメモリデータベースの操作

インメモリデータベースの基本操作を学びます。  
製品は Redis です。  
Redis の基本コマンドに加えて、簡単なチャットシステムを利用して Pub/Sub の仕組みを覗いてみます。  

5. [Redis](./redis/README.md)

## 第8章 実習

SQL インジェクションの実習を行います。  
これからたくさんのコードを書くと思います。セキュリティを意識してコードを書いてもらえると嬉しいです。  

1. [Juice Shop](./juiceshop/README.md)

## 感想
詳細はQiita 記事にアップ  
https://qiita.com/dorayaki800/items/edc77fb26b765778a254  
  
・めんどくさくてなんでもOKの権限を与えるって話、テスト環境構築時とかやりがちだけど「この範囲のものはこういう権限だけにする」っていう最小権限の原則を意識して構築するのが大事








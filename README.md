# 概要
テックキャンプ実装課題
![b0126b950654cf1b3e3203606a517a8f](https://user-images.githubusercontent.com/69582233/110872347-f51e8480-8312-11eb-9aa2-8436a58db5a7.jpg)

## URL
https://protospace-27537.herokuapp.com/

ログイン情報（テスト用）
- Eメール: test@example.com
- password: aaaaaa

※Herokuでデプロイしているため、Herokuの仕様により本番環境にアクセス頂いた際に画像リンクが切れている可能性がございます。


# テーブル設計

## users テーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null :false |
| profile    | text   | null :false |
| occupation | text   | null :false |
| position   | text   | null :false |

### Association
- has_many :prototypes
- has_many :comments


## prototypes テーブル

| Column     | Type       | Options           |
| ---------- | ---------- | ----------------- |
| title      | string     | null: false       |
| catch_copy | text       | nill: false       |
| concept    | text       | nill: false       |
| image      |            |                   |
| user       | references | foreign_key: true |

### Association
- has_many :comments
- belongs_to :user


## comments テーブル

| Column    | Type       | Options           |
| --------- | ---------- | ----------------- |
| text      | text       | null: false       |
| user      | references | foreign_key: true |
| prototype | references | foreign_key: true |

### Association
- belongs_to :user
- belongs_to :prototype




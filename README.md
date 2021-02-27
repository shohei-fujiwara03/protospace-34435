# テーブル設計

## users テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| name     | string | null: false |
| email    | string | null: false |
| password | string | null: false |
| profile | text | null: false |
| occupation | text | null: false |
| position | text | null: false |


### Association

- has_many :prototypes
- has_many :comments

## comments テーブル

| Column | Type   | Options     |
| ------ | ------ | ----------- |
| text   | string | null: false |
| user | reference | null: false, foreign_key: true |
| prototype | reference | null: false, foreign_key: true |


### Association

- belongs_to :user
- belongs_to :prototype

## prototypes テーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| concept | string | null:false |
| catch_copy | text | null: false |
| user | references | null: false, foreign_key: true |


### Association

- belongs_to :user
- has_many :comments
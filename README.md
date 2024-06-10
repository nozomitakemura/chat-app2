# テーブル設計

## users テーブル

| Column             | Type   | Options                              |
| ------------------ | ------ | -----------------------------------  |
| name               | string | null: false                          |
| email              | string | null: false, unique: true            |
| encrypted_password | string | null: false                          |


### Association

- has_many :rooms
- has_many :messages

## user_roomテーブル

| Column               | Type       | Options                        |
| -------------------- | ---------- | ----------                     |
| user                 | references | null: false, foreign_key: true |
| room                 | string     | null: false                    |


### Association

- belongs_to :user
- has_one :order

## room テーブル

| Column      | Type       | Options                        |
| ----------- | ---------- | ------------------------------ |
| room_name   | references | null: false, foreign_key: true |

### Association
- belongs_to :item
- belongs_to :user
- hus_one :address

## messages テーブル
| Column           | Type       | Options                        |
| ---------------- | ---------- | ------------------------------ |
| order            | references | null: false, foreign_key: true |
| postcode         | string     | null: false                    |
| prefecture_id    | integer    | null: false                    |
| municipalities   | string     | null: false                    |
| block            | string     | null: false                    |

### Association

- belongs_to :order

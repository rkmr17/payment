# テーブル設計

## users テーブル

| Column             | Type   | Options                  |
| ------------------ | ------ | ------------------------ |
| email              | string | null: false unique: true |
| encrypted_password | string | null: false              |
| name               | string | null: false              |

### Association

-has_many :payments

## payment テーブル

| Column                | Type       | Options                        |
| --------------------- | ---------- | ------------------------------ |
| amount                | integer    | null: false                    |
| memo                  | text       | null: false                    |
| day                   | date       | null: false                    |
| user                  | references | null: false, foreign_key: true |

### Association

-belongs_to :user
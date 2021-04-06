## users テーブル

| Column   | Type   | option      |
| -------- | ------ | ----------- |
| email    | string | null: false |
| password | string | null: false |
| name     | string | null: false |
| profile  | text   | null: false |
| position | text   | null: false |

### Association
- has_many :prototypes
- has_many :comments

## prototypesテーブル

| Column     | Type       | option                         |
| ---------- | ---------- | ------------------------------ |
| title      | string     | null: false                    |
| catch_copy | string     | null: false                    |
| concept    | string     | null: false                    |
| user       | references | null: false, foreign_key: true |

### Association
- has_many   :comments
- belongs_to :user

## commentsテーブル

| Column     | Type       | option                         |
| ---------- | ---------- | ------------------------------ |
| text       | string     | null: false                    |
| user       | references | null: false, foreign_key: true |
| prototype  | references | null: false, foreign_key: true |

### Association
- belongs_to :prototype
- belongs_to :user

# テーブル設計

## users テーブル

| Column             | Type   | Options                   |
| ------------------ | ------ | ------------------------- |
| email              | string | unique: true, default: "" |
| encrypted_password | string | null: false   default: "" |
| name               | string | null: false   default: "" |
| profile            | text   | null: false   default: "" |
| occupation         | text   | null: false   default: "" |
| position           | text   | null: false   default: "" |


### Association

 has_many :prototypes
 has_many :comments
 

## prototypes テーブル

| Column     | Type       | Options                        |
| -----------| ---------- | ------------------------------ |
| title      | string     | null: false      default: ""   |
| catch_copy | text       | null: false      default: ""   |
| concept    | text       | null: false,     default: ""   |
| user       | references |foreign_key: true default: ""   |

### Association

 belongs_to :users
 has_many   :comments


## comments テーブル

| Column       | Type       | Options                        |
| ------------ | ---------- | ------------------------------ |
| content      | text       | null: false       default: ""  |
| prototype    | references | foreign_key: true default: ""  |
| user         | references | foreign_key: true default: ""  |

### Association

belongs_to :user
belongs_to :prototypes
# README

## users テーブル

| Column                     | Type       | Options                  |
| ---------------------------| -----------| -------------------------|
| nickname                   | string     | null: false              |
| email                      | string     | null: false, unique:true |
| encrypted_password         | string     | null: false              |
| birthday                   | date       | null: false              |
  
### Association

-has_many :diaries
-has_many :comments


## diaries テーブル 

| Column                 | Type       | Options                        |
| -----------------------| -----------| -------------------------------|
| training_menu1_id      | integer    | null: false                    |
| training_menu2_id      | integer    |                                |
| training_menu3_id      | integer    |                                |
| training_menu4_id      | integer    |                                |
| training_menu5_id      | integer    |                                | 
| training_menu6_id      | integer    |                                |
| training_menu7_id      | integer    |                                |
| training_menu8_id      | integer    |                                |
| training_menu9_id      | integer    |                                |
| training_menu10_id     | integer    |                                |
| training_diary         | text       | null: false                    |
| weight                 | integer    | null: false                    |
| height                 | integer    | null: false                    |
| user                   | references | null: false, foreign_key: true |

### Association

-belongs_to :user
-has_many :comments


## comments テーブル

| Column                 | Type       | Options                        |
| -----------------------| -----------| -------------------------------|
| comment                | text       | null: false                    |
| user                   | references | null: false, foreign_key: true |
| diary                  | references | null: false, foreign_key: true |

### Association

-belongs_to :user
-belongs_to :diary



# テーブル設計

## users テーブル
|       Column            | Type        | Options                      |
| ----------------------- | ----------- | ---------------------------- |
| last name               | string      | null: false                  |
| first name              | string      | null: false                  |
| last name(katakana)     | string      | null: false                  |
| first name(katakana)    | string      | null: false                  |
| email                   | string      | null: false                  |
| password                | string      | null: false                  |
| nickname                | string      | null: false                  |
| birthday                |  date       | null: false                  |
| contract                |  references | null: false,foreign_key:true |

### Association
- has_many : contract
- has_one  :property 


## properties テーブル

|     Column         |    Type      |     Options                 |
| ----------------   |  ----------- | ----------------------------|
| image              |    string    | null: false                 |
| property_name      |    string    | null: false                 |
| rent               |    integer   | null: false                 |
| Common_service_fee |    integer   | null: false                 |
| security_deposit   |    integer   | null: false                 |
| key_money          |    integer   | null:false                  |
| company            | references   |null: false,foreign_key: true|

### Association
- belongs_to :companies
- has_one   :users
- has_many :contract


## contracts テーブル

|    Column            |    Type       |   Options                    |
| -------------------- |  -------------| -----------------------------|
| use_id               |    integer    | null: false                  |
| reason_for_moving_id |    integer    | null: false                  |
| last name            |    string     | null: false                  |
| first name           |    string     | null: false                  |
| last name(katakana)  |    string     | null: false                  |
| first name(katakana) |    string     | null: false                  |
| email                |    string     | null: false                  |
| birthday             |    date       | null: false                  |
| sex_id               |    integer    | null: false                  |
| Prefecture_id        |    integer    | null: false                  |
| city                 |    string     | null: false                  |
| house_number         |    string     | null: false                  |
| building_name        |    string     |                              |
| phone_number         |    string     | null: false                  |
| work                 |    string     | null: false                  |
| work_address         |    string     | null: false                  |
| Work_phone           |    string     | null: false                  |
| industry             |    string     | null: false                  |
| type_id              |    integer    | null: false                  |
| length_of_service    |    string     | null: false                  |
| annual_income        |    string     | null: false                  |
| user                 |    references | null: false,foreign_key: true|
| property             |    references | null: false,foreign_key: true|

### Association
- belongs_to :users 
- belongs_to :property
- belongs_to :companies


## companies テーブル
|       Column            | Type   | Options     |
| ----------------------- | ------ | ----------- |
| company_name            | string | null: false |
| email                   | string | null: false |
| password                | string | null: false |

- has_many :property
- has_many :contract


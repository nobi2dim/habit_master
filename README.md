# README

## users テーブル

| Column                |  Type  | Options                   |
| --------------------- | ------ | ------------------------- |
| name                  | string | null: false               |
| email                 | string | null: false, unique: true |
| encrypted_password    | string | null: false               |

### Association

- has_many :habits
- has_many :results
- has_many :avatars



## habits テーブル

| Column       | Type       | Options                        |
| ------------ | ---------- | ------------------------------ |
| habit1       | text       | null: false                    |
| habit2       | text       | null: false                    |
| habit3       | text       | null: false                    |
| habit4       | text       | null: false                    |
| habit5       | text       | null: false                    |
| user         | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_many :results
- has_one :avatar



## results テーブル

| Column      | Type       | Options                        |
| ----------- | ---------- | ------------------------------ |
| date        | date       | null: false                    |
| result1     | integer    | null: false                    |
| result2     | integer    | null: false                    |
| result3     | integer    | null: false                    |
| result4     | integer    | null: false                    |
| result5     | integer    | null: false                    |
| memo        | text       |                                |
| user        | references | null: false, foreign_key: true |
| habit       | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :habit



## jobs テーブル

| Column             | Type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| name               | string     | null: false                    |
| attack_terms       | integer    | null: false                    |
| defense_terms      | integer    | null: false                    |
| intelligence_terms | integer    | null: false                    |
| speed_terms        | integer    | null: false                    |
| lucky_terms        | string     | null: false                    |
| HP_adv             | integer    | null: false                    |
| MP_adv             | integer    | null: false                    |
| attack_adv         | integer    | null: false                    |
| defense_adv        | integer    | null: false                    |
| intelligence_adv   | integer    | null: false                    |
| speed_adv          | integer    | null: false                    |
| lucky_adv          | integer    | null: false                    |

### Association

- has_many :avatars



## avatars テーブル

| Column        | Type       | Options                        |
| ------------- | ---------- | ------------------------------ |
| name          | string     | null: false                    |
| HP            | integer    | null: false                    |
| MP            | integer    | null: false                    |
| level         | integer    | null: false                    |
| attack        | integer    | null: false                    |
| defense       | integer    | null: false                    |
| intelligence  | integer    | null: false                    |
| speed         | integer    | null: false                    |
| lucky         | string     | null: false                    |
| user          | references | null: false, foreign_key: true |
| habit         | references | null: false, foreign_key: true |
| job           | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :habit
- belongs_to :job




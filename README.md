#テーブル設計

## users　テーブル

| Column    | Type   | Options     |
| --------- | ------ | ----------- |
| name      | string | NOT NULL    |
| profile   | text   | NOT NULL    |
| occupation| text   | NOT NULL    |
| position  | text   | NOT NULL    |
| email     | string | NOT NULL    |
| password  | string | NOT NULL    |

###Association
 -has_many :comments
 -has_many :prototypes


 ## prototypes テーブル

| Column     | Type       | Options   |
| ---------- | ---------- | ----------|
| title      | string     | NOT NULL  |
| catch_copy | text       | NOT NULL  |
| concept    | text       | NOT NULL  |
| user       | references |           |

###Association
 -has_many :comments, dependent: :destroy
 -belongs_to :user


 ## comments  テーブル

| Column    | Type       | Options  |
| ----------| -----------| ---------|
| text      | text       | NOT NULL |
| user      | references |          |
| prototype | references |          |

###Association
 -belongs_to :user
 -belongs_to :prototype
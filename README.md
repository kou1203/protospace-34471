# ProtoSpaceのER図

## userテーブル
| Column     | Type   | Options  |
| --------   | ------ | -------- |
| email      | string | NOT NULL |
| password   | string | NOT NULL | 
| name       | string | NOT NULL |
| profile    | text   | NOT NULL |
| occupation | text   | NOT NULL |
| position   | text   | NUT NULL |

### Association
- has_many :contents
- has_many :prototypes
  
## prototypesテーブル

| Column     | Type                | Options  |
| -----------| ------------------- | -------- | 
| title      | string              | NOT NULL |
| catch_copy | text                | NOT NULL |
| concept    | text                | NOT NULL |
| image      | ActiveStorageで実装 | NONE     |
| user       | references          | NONE     |

### Association

- belongs_to :user
- has_many :contents

## contentsテーブル
| Column    | Type       | Options  |
| --------- | ---------- | -------- |
| text      | text       | NOT NULL |
| user      | references | NONE     |
| prototype | references | NONE     |

### Association

- belongs_to :users
- belongs_to :prototypes



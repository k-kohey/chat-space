# DB設計

## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## massageテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|blob||
|group_id|integer|foreign_key:true|
|user_id|integer|foreign_key:true|

### Association
- belongs_to :group
- belongs_to :user

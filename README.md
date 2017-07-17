# DB設計

## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
 - belongs_to :user
 - belongs_to :group

## massageテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string||
|group_id|integer|null: false, foreign_key:true|
|user_id|integer|null: false, foreign_key:true|

### Association
- belongs_to :group
- belongs_to :user

## userテーブル
|Column|Type|Options|
|------|----|-------|
|name|text|null: false, index: true, unique: ture|

### Association
- has_many :massage
- has_many :group , through  :members
- has_many :members

## groupテーブル   
|Column|Type|Options|
|------|----|-------|
|name|text|null: false, unique: true|

### Association
- has_many :massage
- has_many :user, through :members
- has_many :members 

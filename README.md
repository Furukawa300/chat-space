## DB設計
## users table
|Column|Type|Options|
|------|----|-------|
|name|string|index: true, null: false, unique: true|
|mail|string|null: false|
|password|string|null: false|
### Association
- has_many :groups, through: :members
- has_many :messages
- has_many :members

## groups table
|Column|Type|Options|
|------|----|-------|
|name|string|index: true, null: false, unique: true|
## Association
- has_many :members
- has_many :massages
- has_many :users, through: :members


## members テーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :groups
- belongs_to :users
- has_many :messages


## messages table
|Column|Type|Options|
|------|----|-------|
|name|string|index: true, null: false, unique: true|
|image|string||
|text|text||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :users
- belongs_to :groups


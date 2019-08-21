## DB設計
## user table
|Column|Type|Options|
|------|----|-------|
|name|string|index: true, null: false, unique: true|
|mail|string|null: false|
|password|string|null: false|
|nickname|string|null: false|
### Association
- has_many :groups, through: members
- has_many :messages
- has_many :members

## group table
|Column|Type|Options|
|------|----|-------|
|id|string|index: true, null: false, unique: true|
## Association
- has_many :members
- has_many :massages
- has_many :users, through: members


## member テーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :groups
- belongs_to :users
- has_many :messages


## message table
|Column|Type|Options|
|------|----|-------|
|name|string|index: true, null: false, unique: true|
|mail|string|null: false|
|image|text||
text|text||
### Association
- has_many :users
- has_many :groups
- has_many :members


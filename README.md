# README



## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|index :true, null: false, unique: true|
|mail|string|null: false, unique: true|

## Association
- has_many :groups, through: :members
- has_many :messages
- has_many :members


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|index :true, null: false|
|mail|string|null: false|
|group|refarences|null: false, foreign_key:true|
|user|refarences|null: false, foreign_key:true|

### Association
- belongs_to :user
- belongs_to :group


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|groupname|string|null: false, unuique: true|

### Association
- belongs_to :users, through: :members
- has_many :members
- has_many :messages







# README

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


## users table

|Culumn|Type|Opton|
|------|----|-----|
|name|string|index: true, null:false, unque: true|
|mail|string|null: false|

### Association
- has_many :groups, through: groups_users
- has_many :groups_users
- has_many :messages

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|image|text||
|text|text||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_ to :group

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|index: true, null:false,unque: true|

### Association
- has_many :users, :through: groups_users
- has_many :groups_users
- has_many :messages
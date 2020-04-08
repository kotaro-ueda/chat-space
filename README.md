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
- has_many :groups, through: members
- has_many :messages
- has_many :members

## chatsテーブル
|Column|Type|Options|
|------|----|-------|
|image|text||
|text|text||
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group|string|index: true, null:false,unque: true|

### Association
- has_many :groups
- has_many :users
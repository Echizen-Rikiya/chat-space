# README

## usersテーブル

|Colum|Type|Options|
|-----|----|-------|
|user_id|integer|null: false|unique|
|name|string|null: false|
|mail|string|null: false|

has_many :groups, through: :group_users

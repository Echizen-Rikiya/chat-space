# chat-space

## usersテーブル

|Colum|Type|Options|
|-----|----|-------|
|name|string|null: false|
|mail|string|null: false, unique: true|
|password|integer|null: false|
### Association

- has_many :groups, through: :groups_users
- has_many :groups_users
- has_many :message

## groupsテーブル

|Colum|Type|Options|
|-----|----|-------|
|name|string|null: false|
### Association

- has_many :users, through: :groups_users
- has_many :groups_users
- has_many :messages

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


### messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belong_to :user
- belong_to :group

# DB設計
usersテーブル
|Column|Type|Options|
|------|----|-------|
|nickname|string|null :false|
|password|string|null :false|
|email|string|null :false|
- has many :tweets
- has many :groups_users
- has many :groups, through: :groups_users 

tweetsテーブル
|Column|Type|Options|
|------|----|-------|
|image|text|||
|text|text|||
|group|references|null :false foreign_key :true|
|user|references|null :false foreign_key :true|
- belongs_to :user
- belong_to :group

groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string||null :false|
- has many :users, through: :groups_users
- has_many :tweets
- has_many :groups_users

groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|group|references|null :false foreign_key :true|
|user|references|null :false foreign_key :true|
- belong_to :group
- belong_to :user

# DB設計
usersテーブル
|Column|Type|Options|
|------|----|-------|
|nickname|string|null :false|
|password|string|null :false|
|email|string|null :false|
- has many :tweets
- has many :groups 

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
- belong_to :users
- has_many :tweets
- has_many :members  through:  :groups_members

membersテーブル
|Column|Type|Options|
|------|----|-------|
|user_name|string||null :false|
|group|refences|null :false foreign_key :true
- has_many :groups_members
- has_many :groups  through:  :groups_members

groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|group|refences|null :false foreign_key :true|
|user|refences|null :false foreign_key :true|
- belong_to :group
- belong_to :member
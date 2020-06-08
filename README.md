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
|user_id|integer|null :false foreign_key :true
- belongs_to :user
- has many :groups

groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|string||null :false|
|member_id|integer|null :false foreign_key :true
- belongs_to :user
- has_many :tweets
- has_many :groups_members
- has_many :members  through:  :groups_members

membersテーブル
|Column|Type|Options|
|------|----|-------|
|user_name|string||null :false|
|group_id|integer|null :false foreign_key :true
- has_many :groups_members
- has_many :groups  through:  :groups_members

groups_membersテーブル
|Column|Type|Options|
|------|----|-------|
|group_id|integer|null :false foreign_key :true|
|member_id|integer|null :false foreign_key :true|
- belong_to :groups
- belong_to :members
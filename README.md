# README.md

usersテーブル

|Column|Type|Options|
|------|----|-------|
|nickname|string|null :false|
|password|string|null :false|
|email|string|null :false|

- has many :tweets
- has many :comments

tweetsテーブル

|Column|Type|Options|
|------|----|-------|
|image|text|||
|text|text|||
|user_id|integer|null :false foreign_key :true

- belongs_to :user
- has many :comments

|Column|Type|Options|
|------|----|-------|
|text|text||null :false|
|user_id|integer|null :false foreign_key :true
|tweet_id|integer|null :false foreign_key :true

- belongs_to :user
- belongs_to :tweet
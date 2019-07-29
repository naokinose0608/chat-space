# Usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null:false|
|email|string|null:false|
|pasward|string|null:false|

### Association
- has_many : groups, through: : members
- has_many : messages
- has_many : members

# Groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null:false|
### Association
- has_many : messages
- has_many : members
- has_many : users, through: :members


# Membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null:false, foreign_key: true|
|group_id|integer|null:false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

# Massagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|user_id|integer|null:false, foreign_key: true|
|group_id|integer|null:false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group
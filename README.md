# Userテーブル

|Column|Type|Options|
|------|----|-------|
|name|text|null:false|
|email|string|null:false|
|pasward|string|null:false|

### Association
- has_many : group
- has_many : message

# Groupテーブル

|Column|Type|Options|
|------|----|-------|
|name|text|null:false|
|user_id|integer|null:false, foreign_key: true|
### Association
- has_many :menbers
- has_many :message, through: :menbers

# Membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null:false, foreign_key: true|
|group_id|integer|null:false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

# Massageテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|null:false|
|image|string|null:false|
|user_id|integer|null:false, foreign_key: true|
|group_id|integer|null:false, foreign_key: true|

### Association
- belongs_to :user

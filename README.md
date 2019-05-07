## users table

|Column|Type|Options|
|------|----|-------|
|name|string|index: true, null: false, unique: true|
|e-mail|string|null: false, unique: true|

### Association
- has_many :groups, through: members
- has_many :messages
- has_many :members


## groups table

|Columns|Type|Options|
|-------|----|-------|
|name|string|null: false, unique: true|

### Association
- has_many :users, through: members
- has_many :members
- has_many :messages


## messages table

|Columns|Type|Options|
|-------|----|-------|
|body|text|null: false|
|image|string||
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


## members table

|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


## users table

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true|
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
- has_many :users


### messages table

|Columns|Type|Options|
|-------|----|-------|
|body|text|null: false|
|image|string|null: true|

### Association
- belongs_to :user


## members table

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


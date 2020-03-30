## userテーブル

|column|type|options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|

### association
- has_many :messages
- has_many :groups, through: :users_groups
- has_many :users_groups


## groupsテーブル

|column|type|options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :messages
- has_many :users, through: :users_groups
- has_many :users_groups


## users_groupsテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


## messagesテーブル

|column|type|options|
|------|----|-------|
|body|text||
|image|string||
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user







#DB設計

## users table
|Column               | Type        | Options       |
|---------------------|-------------|---------------|
|nickname             |string       |null:false     |
|email                |string       |null:false     |
|encrypted_password   |string       |null:false     |
|first_name           |string       |null:false     |
|first_name_kana      |string       |null:false     |
|family_name          |string       |null:false     |
|family_name_kana     |string       |null:false     |
|birth_day            |date         |null:false     |

### Association
* has_many :items 
* has_many :orders
* belongs_to :addresses

## addresses table
|Column               |Type         |Options                    |
|---------------------|-------------|---------------------------|
|post_code            |string       |null:false                 |
|prefecture           |string       |null:false                 |
|city                 |string       |null:false                 |
|address              |string       |null:false                 |
|building_name        |string       |                           |
|phone_number         |string       |                           |

### Association
* belongs_to :user

## orders table

|Column               |Type         |Options                    |
|---------------------|-------------|---------------------------|
|nickname             |string       |null:false                 |
|image                |string       |                           |
|price                |string       |null:false                 |
|category             |integer      |null:false,foreign_key:true|
|shipping_cost        |string       |null:false                 |
|shipping_days        |string       |null:false                 |
|prefecture           |integer      |null:false,foreign_key:true|

### Association
* belongs_to :user

## item table
|Column               |Type         |Options                    |
|---------------------|-------------|---------------------------|
|nickname             |string       |null:false                 |
|price                |string       |null:false                 |
|description          |string       |null:false                 |
|status               |string       |null:false                 |
|shipping_cost        |string       |null:false                 |
|shipping_days        |string       |null:false                 |
|prefecture           |string       |null:false                 |
|category             |integer      |null:false,foreign_key:true|

### Association
* belongs_to :user


#DB設計

## users table
|Column               | Type        | Options       |
|---------------------|-------------|---------------|
|nickname             |string       |null:false     |
|email                |string       |null:false     |
|encrypted_password   |string       |null:false     |
|user_image           |string       |               |
|first_name           |string       |null:false     |
|first_name_kana      |string       |null:false     |
|family_name          |string       |null:false     |
|family_name_kana     |string       |null:false     |
|birth_day            |date         |null:false     |

### Association
* has_many :items 
* belongs_to :destination 

## destination table
|Column               |Type         |Options                    |
|---------------------|-------------|---------------------------|
|user_id              |integer      |null:false,foreign_key:true|
|first_name           |string       |null:false                 |
|first_name_kana      |string       |null:false                 |
|family_name          |string       |null:false                 |
|family_name_kana     |string       |null:false                 |
|post_code            |string       |null:false                 |
|prefecture           |string       |null:false                 |
|city                 |string       |null:false                 |
|address              |string       |null:false                 |
|building_name        |string       |                           |
|phone_number         |string       |                           |

### Association
* belongs_to :user

## item table
|Column               |Type         |Options                    |
|---------------------|-------------|---------------------------|
|name                 |string       |null:false                 |
|price                |string       |null:false                 |
|description          |string       |null:false                 |
|status               |string       |null:false                 |
|size                 |string       |null:false                 |
|shipping_cost        |string       |null:false                 |
|shipping_days        |string       |null:false                 |
|prefecture           |string       |null:false                 |
|category_id          |integer      |null:false,foreign_key:true|
|brand_id             |integer      |null:false,foreign_key:true|
|shipping_id          |integer      |null:false,foreign_key:true|

### Association
* belongs_to :user
* belongs_to :category
* belongs_to :brand
* has_many :images

## card table
|Column              |Type          |Options                    |
|--------------------|--------------|---------------------------|
|user_id             |integer       |null:false,foreign_kye:true|
|customer_id         |string        |null:false                 |
|card_id             |string        |null:false                 |

### Association
* belongs_to :user


## image table
|Column              |Type          |Options                    |
|--------------------|--------------|---------------------------|
|image               |string        |null:false                 |
|item_id             |integer       |null:false,foreign_key:true|

### Association
* belongs_to :item

## category table
|Column             |Type           |Options                    |
|-------------------|---------------|---------------------------|
|name               |string         |null:false                 |
|type               |string         |                           |

### Association
* has_many :items

## brand table
|Column            |Type            |Options                   |
|------------------|----------------|--------------------------|
|name              |string          |index:true                |

### Association
* has_many :items
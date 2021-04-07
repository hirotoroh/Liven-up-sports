# README

# テーブル設計

## usersテーブル

| Column             | Type   | Option                   |
| ------------------ | ------ | ------------------------ |
| email              | string | unique: true, null: false|
| encrypted_password | string | null: false              |
| nickname           | string | null: false              |
| sports             | string | null: false              |
| gender             | string | null: false              |
| age                | string | null: false              |

### Association
- has_many :tweets
- has_many :comments

## tweetsテーブル

| Column      | Type       | Option                         |
| ----------- | ---------- | ------------------------------ |
| title       | string     | null: false                    |
| video_url   | string     | null: false                    |
| description | text       | null: false                    |
| user        | references | null: false, foreign_key: true |

### Association
- belongs_to :user
- has_many :comments

## commentsテーブル
| Column      | Type       | Option                         |
| ----------- | ---------- | ------------------------------ |
| content     | string     |                                |
| user        | references | null: false, foreign_key: true |
| tweet       | references | null: false, foreign_key: true |

### Association
- belongs_to :user
- belongs_to :tweet

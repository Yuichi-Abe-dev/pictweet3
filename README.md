## users テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| nickname | string | null: false |
| email    | string | null: false |
| password | string | null: false |

### Association

- has_many :tweets
- has_many :comments

## tweets テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| text     | string | null: false |
| image    | string | null: false |
| user_id  | string | null: false |

### Association
- belongs_to :user
- has_many :comments

## comments テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| text     | string | null: false |
| image    | string | null: false |
| user_id  | string | null: false |
| tweet_id | string | null: false |

### Association
- belongs_to :user
- belongs_to :tweet

## コピーの手順

### projectsディレクトリに移動
% cd

% cd projects

### マスターからディレクトリをダウンロードする
% git clone https://github.com/Yuichi-Abe-dev/pictweet3.git

### マスターからディレクトリをダウンロードする
% git clone -b ブランチ名 https://github.com/Yuichi-Abe-dev/pictweet3.git

### pictweet3に移動
% cd pictweet3

### Gemfileの末尾に以下を追記
gem 'rename'

### Gemをインストール
% bundle install

### アプリ名の変更
rails g rename:into <変更後の名前>

### JavaScriptのパッケージをインストール
% yarn install

### データベースの再生成
% rails db:migrate:reset

### サーバーを立ち上げる
% rails s

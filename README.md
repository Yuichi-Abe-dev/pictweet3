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
```
% cd
% cd projects
```
### マスターからディレクトリをダウンロードする
```
% git clone https://github.com/Yuichi-Abe-dev/pictweet3.git
```
### マスターからディレクトリをダウンロードする
```
% git clone -b ブランチ名 https://github.com/Yuichi-Abe-dev/pictweet3.git
```
### pictweet3に移動
```
% cd pictweet3
```
### ※Gemfileの末尾に以下を追記
```
gem 'rename'
```
### Gemをインストール
```
% bundle install
```
### ※アプリ名の変更
```
% rails g rename:into <変更後の名前>
```

もしくは、config/application.rbの９行目moduleに続くアプリ名を手動で変更

### JavaScriptのパッケージをインストール
```
% yarn install
```
### データベースの再生成
```
% rails db:migrate:reset
```
### サーバーを立ち上げる
```
% rails s
```

## データベースにテストデータの追加

### コンソールを起動
```
rails c
```
### ユーザーの追加
```
pry(main)> User.create(nickname: "test1", email: "test1@test.com", password: "11111111")
pry(main)> User.create(nickname: "test2", email: "test2@test.com", password: "11111111")
```

### 投稿の追加
```
pry(main)> Tweet.create(text: "post1", image: "https://www.pakutaso.com/shared/img/thumb/kumakichi0221011_TP_V.jpg", user_id: "1")
pry(main)> Tweet.create(text: "post2", image: "https://static.amanaimages.com/imgroom/rf_preview640/10860/10860000316.jpg", user_id: "1")
pry(main)> Tweet.create(text: "post3", image: "https://www.pakutaso.com/shared/img/thumb/RED20124076_TP_V.jpg", user_id: "2")
pry(main)> Tweet.create(text: "投稿テスト4", image: "https://www.pakutaso.com/shared/img/thumb/kumakichi0221011_TP_V.jpg", user_id: "2")
```

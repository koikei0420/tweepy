# tweepy
- A,B,Cさんが共にフォローしている人を自動でリストアップするツール
- Tweepy.ipynb, tweepy.pyともに同じコード

## 使い方

### Twitter Developer Account Credentialsを自分のものに変える
```python
# Twitter Developer Account Credentials
consumer_key = 'hogehoge'
consumer_secret = 'hogehoge'
access_token = 'hogehoge'
access_token_secret = 'hogehoge'
```

### A,B,CさんのIDを指定
```python
# 影響力のある人のID（複数人可能）
user_ids = [
    'AAA',
    'BBB',
    'CCC'
]
```

### 独自関数

#### my_auth (consumer_key, consumer_secret, access_token, access_token_secret) / return tweepy.API
- Twitter API と接続

##### 引数
- [必須]consumer_key, consumer_secret, access_token, access_token_secret： Twitter Developer Account Credentials

##### 戻り値
- tweepy.API

***

#### friends_common_part(api, *args) / return candidate_dict
- A,B,C...さんに共通するフォロワーのリストを返す
##### 引数
- [必須]api: tweepy.API
- [必須]*args： A, B, C…さんのTwitter ID(screen name)が入った可変長配列。少なくとも２つのIDが必要

##### 戻り値
- candidate_dict: 候補者の`id`, `name`, `twitter_page`, `description`, `my_page`を含む辞書型
- `{ id: {name: 'hoge', twitter_page: 'hogehoge', description: 'fuga', my_page: 'fugafuga'}, ...}`

***

#### followers_common_part(api, *args) / return candidate_dict
- A,B,C...さんに共通するフォロイーのリストを返す
##### 引数
- [必須]api: tweepy.API
- [必須]*args： A, B, C…さんのTwitter ID(screen name)が入った可変長配列。少なくとも２つのIDが必要

##### 戻り値
- candidate_dict: 候補者の`id`, `name`, `twitter_page`, `description`, `my_page`を含む辞書型
- `{ id: {name: 'hoge', twitter_page: 'hogehoge', description: 'fuga', my_page: 'fugafuga'}, ...}`

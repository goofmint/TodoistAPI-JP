# JSONのプロパティについて

日時はUTCになります。形式は以下のようになります。

```
{
  "start_page": "_info_page",
  "api_token": "d18a76ab310947100kc60fe9b3cdc466515bb3a1",
  "time_format": 0,
  "sort_order": 0,
  "full_name": "Joh Doe",
  "mobile_number": "",
  "mobile_host": "",
  "timezone": "Europe/Copenhagen",
  "id": 1,
  "date_format": 1,
  "premium_until": "Sat Sep 22 13:15:03 2018",
  "default_reminder": "no_default",
  "email": "john@doe.com"
}
```

## プロパティの説明

- id: ユーザのユニークID
- api_token: ユーザのトークン。これは他のAPIメソッドをコールする時に使います。
- email: メールアドレス
- full_name: ユーザの名前
- start_page: ユーザのTodoistにおけるデフォルトビュー。例として以下があります。
  - _info_page // インフォページを表示
  - _blank // ブランクページを表示
  - _project_23 // プロジェクト23のページを表示
  ... // もし空でなければクエリーに利用
- timezone: ユーザのタイムゾーン
- tz_offset: ユーザのタイムゾーンオフセット
- time_format: 0だったら24時間表記。それ以外はAM/PM。
- date_format: 0だったらDD-MM-YYYY表記。それ以外だったらMM-DD-YYYY。
- sort_order: 0だったら古い順。それ以外なら新しい順。
- mobile_number: ユーザの携帯電話番号。
- mobile_host: ユーザのモバイルホスト。
- premium_until: プレミアム有効期限。
- default_reminder: リマインダーはプレミアムのみです。以下のパターンがあります。
  - email: メール
  - mobile: モバイル
  - push: プッシュ
  - no_default: デフォルトなし

## /API/login

**HTTPSを使うべきです**

Todoistへのログイン処理を行ってトークンを取得します。他のメソッドをコールする時にはトークンが必要です。

### パラメータ

- email: メールアドレス
- password: パスワード

### 返却値

#### 成功時

HTTP 200が返ってきて、かつ次のようなユーザデータがJSONで返ってきます。

```
{
  "email": "...",
  "token": ...,
  ...
}
```

### 失敗時

"LOGIN_ERROR"

## /API/loginWithGoogle

**HTTPSを使うべきです**

## /API/ping
## /API/getTimezones
## /API/register
## /API/deleteUser
## /API/updateUser
## /API/updateAvatar



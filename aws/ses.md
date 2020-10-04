# Amazon Simple Email Service(SES)

フルマネージド型/サーバレス型のコスト効率に優れたEメールサービス

- スケーラブルな構成で信頼性が高いマネージド型
- メール送信: トランザクションメールなどの高品質なコンテンツを顧客に送信可能
- メール受信: 受信したメールをトリガーに S3 や Lambda などを起動可能
- バウンス処理: メールが送れなかった場合の処理を規定

## メール送信方法

- HTTP REST API
  - SendEmail API: From / To / Subject / Body だけ用意すれば SES 側でメッセージを生成して送信する
  - SendRawEmail API: メッセージ全体をアプリケーション側で生成して送信する
  - 認証: AWS アクセスキーとシークレットアクセスキーを使用
- SMTP エンドポイント
  - 生成済み Email メッセージを受け取って SES の SMTP エンドポイントを経由してメールを送信する。 SMTP を前提としてプログラムから直接利用する場合などに利用
  - 利用ポート
    - 25
    - 465（SMTP over SSL）
    - 587（Message Submission）
  - TLS（Transport Layer Security）が必要
  - 認証: 専用 IAM ユーザを作成してそのクレデンシャルを使用

## メール受信

- SES のメール通知を利用して S3 や Lambda などと連携が可能

## 利用準備

- ドメインを登録
- メールの事前申請

SNSとの違いは？？？

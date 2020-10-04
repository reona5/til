# Amazon Simple Queue Service(SQS)

プロセス間通信などのスレッド間通信に使われるコンポーネントで制御やデータを伝達するポーリング型キューサービス

## ポーリングとは

- 複数のプログラム通信に対し、一定のタイミングの問い合わせがあった場合に送受信処理を行う通信方式
  - 直接通信だと受信側が Busy な場合に処理が滞る可能性がある
  - 一旦中継所に通信内容を貯めておいて、受信側のタイミングがいいときに通信を行う

## 特徴

- 複数のサーバー/データセンターにメッセージを保持する高可用性構成
- 多数の送信者と受信者に対応可能なスケーラビリティの確保
- メッセージが増加しても高スループットを維持できる
- 無料枠と従量課金による低コスト
  - 基本的には 256KB までの軽いデータしか利用できず、60秒から14日間メッセージを保持できる
    - Extended Client Library を利用すると、2GB までのメッセージの送受信が可能
    - 削除されないメッセージはデフォルトで4日間保持
    - 1つのキューごとに最大120,000 In Flight（受信されたメッセージ & Visibility Timeout 内）メッセージ

## キューのタイプ

- 標準キュー
  - 基本的には**なるべく**順番通り
- FIFOキュー
  - 最初に入ったキューを最初に処理する順番を守るキューイングを実施

## 機能

- Short Poling
  - キューが空の場合でも即時にリターンする
- Long Poling
  - キューが空の場合はタイアウトまで待つ
- デッドレターキュー
  - ずっと残ったメッセージを別キューに移動し、正常に処理できなかったメッセージを隔離できる
- Visibility timeout
  - 新しいメッセージを指定時間見えなくする
  - 優先的に処理して欲しい受信インスタンスを指定することが可能
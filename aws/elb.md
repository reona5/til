# Elastic Load Balancing(ELB)

アプリケーションへのトラフィックを複数のターゲット (Amazon EC2 インスタンス、コンテナ、IP アドレスなど) に自動的に分散するロードバランサー

- インスタンス間の負荷を分散する
- 異常なインスタンスを認識して対応する
- パブリック・プライベートどちらでも使用可能
- ELB自体も負荷に応じてキャパシティを自動増減するスケーリングを実施
- 従量課金制
- マネージドサービスなので管理が不要
- Auto Scailing, Route 53, Cloud Formation などと連携

## 基本機能

- ヘルスチェック
- 負荷分散
- SSLサポート
- スティッキーセッション
- Connection Draining
- S3 へのログ保管

- スケーラビリティの確保
- 高可用性

## ELBのタイプ

- Classic Load Balancer(CLB)
- Application Load Balancer(ALB)
  - ALB が使われることが標準
  - ALB はパスルーティングにより CLB より容易にバランシング構成が可能
- Network Load Balancer(NLB)
  - 高負荷が予想されるようなシステムに使われる

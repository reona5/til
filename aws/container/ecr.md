# Elastic Container Registry(ECR)

フルマネージド型のレジストリサービスで Docker コンテナイメージを簡単に保存、管理、デプロイが可能

- ECS と Docker CLI に統合されており、開発から本稼働までのワークフローを簡略化する
- IAM による強力な認証管理機構
- エンドポイントにアクセスできるなら AWS 外からでも利用可能
- ライフサイクルポリシーでイメージの自動クリーンアップができる
- VPC ネットワークモードでタスクごとに ENI を自動割当して、更にセキュリティグループをタスクごとに設定可能

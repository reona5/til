# Amazon Elastic Container Service(ECS)

Docker コンテナをサポートする拡張性とパフォーマンスに優れたコンテナオーケストレーションサービス

- コンテナ化されたアプリを AWS において簡単に実行及びスケールできる
- Fargate を利用することでコンテナのデプロイと管理にサーバーのプロビジョニングや管理は不要
- あらゆる種類のコンテナ化されたアプリケーションを簡単に作成できる
- Docker コンテナの数が数十であっても数万であっても数秒で簡単に起動
- ELB / VPC / IAM / ECR / CloudWatch / CloudFormation / CloudTrail などの AWS サービスを利用可能
- VPC ネットワークモードで Task 毎に ENI を自動割当 Security Group を Task 毎に設定可能
  - VPC 内の他のリソースへ Private IP で通信が可能
- Fargate 起動タイプと EC2 起動タイプという 2種類のモードがある

## コンテナ

- コンテナはホストマシンのカーネルを利用し、プロセスやユーザなどを隔離する仮想化方式

### Docker

Docker はコンテナ型の仮想環境を作成、配布、実行するためのプラットフォーム

#### Amazon のコンテナ（Docker）サービス

- レジストリ => コンテナエンジンに実行されるイメージが保管される場所
  - Amazon ECR
- コントロールプレーン => コンテナを管理するサービス
  - Amazon ECS
  - Amazon EKS
- データプレーン => コンテナが実行される環境
  - AWS Fargate

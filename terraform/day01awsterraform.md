# Day1: Terraform基礎（VPC・サブネット）

## 学習日
2026-01-11

## 学んだこと

### IaC（Infrastructure as Code）とは
- インフラをコードで管理する手法
- 手動でコンソール操作するのではなく、コードで定義
- バージョン管理、再現性、自動化が可能

### Terraformの基本コマンド

| コマンド | 役割 |
|----------|------|
| `terraform init` | 初期化（プロバイダー取得） |
| `terraform plan` | 変更内容を確認（実行前プレビュー） |
| `terraform apply` | 実際に作成・変更 |
| `terraform destroy` | リソース削除 |

### 基本サイクル
```
main.tf を書く → plan（確認） → apply（作成） → destroy（削除）
```

### planの出力記号

| 記号 | 意味 |
|------|------|
| `+ create` | 新規作成 |
| `~ update` | 変更 |
| `- destroy` | 削除 |

### 作成したリソース
- VPC（learning-vpc）: 10.0.0.0/16
- サブネット（learning-public-subnet）: 10.0.1.0/24

### デフォルトVPC
- AWSアカウント作成時に自動で作られる
- 自分で設計したVPCを使う

## Gitブランチ運用
- `git checkout -b feature/xxx` で新規ブランチ作成+切り替え
- 作業後にPull Request → Merge
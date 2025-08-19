# Amazon Verified Permissions ペットストア サンプル

**注意: このサンプルはデモ目的で設計されており、本番環境での使用を想定していません。**

このプロジェクトは、Amazon Cognito による認証を使用する Node.js/Express アプリケーションに Amazon Verified Permissions を統合する方法を示します。ペットストアの完全な動作例を、以下の2つのバージョンで提供します。

1. **Start 版**: 認可制御を含まないベースラインのアプリケーション
2. **Finish 版**: Cedar と Verified Permissions の Express 向けパッケージ（`@verifiedpermissions/authorization-clients` および `@cedar-policy/authorization-for-expressjs`）を用いて Verified Permissions を統合し、認可を実装したアプリケーション

## プロジェクト構成

```
AVPPetStoreCognitoSample/
├── start/                  # AVP 未統合のベースライン アプリケーション
│   ├── backend/            # Express.js API バックエンド
│   ├── frontend/           # Web フロントエンド アプリケーション
│   └── scripts/            # セットアップ/デプロイ用ユーティリティ スクリプト
│
├── finish/                 # AVP を統合した完成版アプリケーション
│   ├── backend/            # AVP 認可を備えた Express.js API
│   ├── frontend/           # Web フロントエンド アプリケーション
│   └── scripts/            # セットアップ/デプロイ用ユーティリティ スクリプト
```

## はじめに

各バージョン（start / finish）には、それぞれ固有のセットアップ手順を記した README が含まれています。一般的な手順は次のとおりです。

1. 必要な AWS リソースの作成（Cognito、DynamoDB、AVP）
2. 環境変数の設定（必要に応じてデフォルトから変更）
3. 依存関係のインストール
4. アプリケーションの実行

## 前提条件

- Node.js 16 以上
- npm 7 以上
- 次のリソースを作成できる権限を持つ AWS アカウント
  - Cognito ユーザープール
  - DynamoDB テーブル
  - Verified Permissions ポリシーストア
- ローカル環境で設定済みの AWS CLI

## 参考資料

- [Amazon Verified Permissions ドキュメント](https://docs.aws.amazon.com/verified-permissions/)
- [Cedar](https://docs.cedarpolicy.com/)
- [Amazon Cognito ドキュメント](https://docs.aws.amazon.com/cognito/)
- [Express.js ドキュメント](https://expressjs.com/)

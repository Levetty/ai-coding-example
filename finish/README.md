# ペットストア サンプルアプリケーション

これは React フロントエンドと Express.js バックエンドで構成されたサンプルアプリケーションです。`finish` バージョンには、Amazon Verified Permissions を統合するための追加コード、Cedar スキーマ、Cedar ポリシーが含まれています。

## プロジェクト構成

`finish` プロジェクトは次の3つのディレクトリで構成されています。

```
start/
├── backend/       # Express.js の API サーバー
├── frontend/      # React の Web アプリケーション
└── scripts/       # 開発・デプロイ用のユーティリティスクリプト
```

## バックエンド

バックエンドは、ペットの管理用 RESTful API を提供する Express.js アプリケーションです。エンドポイントは次のとおりです。

- `GET /health` - サービスのヘルスチェック
- `GET /api/pets` - すべてのペット一覧
- `GET /api/pets/:id` - ペット詳細の取得
- `POST /api/pets` - ペットの作成
- `PUT /api/pets/:id` - ペットの更新
- `DELETE /api/pets/:id` - ペットの削除

## フロントエンド

フロントエンドは次のページを含む React アプリケーションです。

- **Dashboard** - ペットの概要
- **Pet List** - ペットの一覧・管理
- **Pet Details** - ペット情報の閲覧・編集
- **Create Pet** - 新規ペットの追加

## スクリプト群

`scripts` ディレクトリには、開発、デプロイ、インフラ構築向けのユーティリティスクリプトが含まれます。

- `run-backend-dev.sh` - バックエンドを開発モードで起動
- `run-frontend-dev.sh` - フロントエンドを開発モードで起動
- `setup-infrastructure.sh` - 必要な AWS インフラをセットアップ
- `prepare-cedar-schema.sh` - AWS CLI で利用する Cedar スキーマ形式へ更新
- `convert_cedar_policies.sh` - AWS CLI で利用する Cedar ポリシー形式へ更新

## はじめに

### 前提条件

- Node.js 16 以上
- npm 7 以上
- 次のリソースを作成できる権限を持つ AWS アカウント
  - Cognito ユーザープール
  - DynamoDB テーブル
  - Verified Permissions ポリシーストア
- ローカル環境で設定済みの AWS CLI

### 初回セットアップ
アプリケーションを初めて実行する際は、以下の手順に従ってください。

1. **インフラのセットアップ**
設定済みの AWS アカウントに Cognito ユーザープールと DynamoDB テーブルを作成します。
    ```bash
    cd scripts
    ./setup-infrastructure.sh
    ```
2. **アプリケーションの起動**
依存関係のインストールと基本的な環境設定を行います。次を 2 つのターミナルで実行します。
    ```bash
    cd scripts
    ./run-backend-dev.sh
    ```
    ```bash
    cd scripts
    ./run-frontend-dev.sh
    ```

3. **アクセス方法:**
   - フロントエンド: http://localhost:3001
   - バックエンド API: http://localhost:3000


### 開発ワークフロー
初期セットアップ後にアプリケーションを起動する手順は次のとおりです。

1. **アプリケーションを起動**
別々のターミナルで実行します。
   ```bash
   cd backend
   npm run dev
   ```
   ```bash
   cd frontend
   npm start
   ```
2. **アクセス方法**
   - フロントエンド: http://localhost:3001
   - バックエンド API: http://localhost:3000

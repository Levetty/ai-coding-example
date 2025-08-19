# バックエンド API

この Express.js バックエンドは、ペットストアアプリケーション向けのシンプルな API を提供します。`start` バージョンには認可機能がありません。


## ディレクトリ構成

```
src/
├── app.ts              # ミドルウェアとルートを含む Express アプリケーションのセットアップ
├── index.ts            # 開発・本番環境共通の単一エントリーポイント
├── types.ts            # TypeScript 型定義
├── config/             # 設定管理
├── middleware/         # ミドルウェア実装
├── routes/             # API ルートハンドラー
├── controllers/        # ビジネスロジック コントローラー
└── utils/              # ユーティリティ関数とログ機能
```

## 設定

アプリケーションは環境変数を使用して設定を行います。

```bash
# サーバー設定
PORT=
NODE_ENV=
# AWS 設定
AWS_REGION=
# DynamoDB 設定
DYNAMODB_PETS_TABLE=
```

## API エンドポイント

- `GET /health` - サービスのヘルスチェックと設定詳細を返す
- `GET /api/pets` - すべてのペット一覧
- `GET /api/pets/:id` - 特定のペット詳細を取得
- `POST /api/pets` - 新規ペットを作成
- `PUT /api/pets/:id` - 既存のペットを更新
- `DELETE /api/pets/:id` - ペットを削除


## 開発用コマンド

```bash
# ホットリロード付き開発モード
npm run dev
# 型チェック
npm run type-check
# リンティング
npm run lint
# ビルド
npm run build
# ビルド版を起動
npm start
```
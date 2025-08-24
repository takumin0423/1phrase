# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## プロジェクト概要

**1phrase**は、Next.js（フロントエンド）とHono（バックエンドAPI）を使用したモノレポ構造のWebアプリケーションです。Cloudflare Workersへのデプロイに最適化されています。

## 技術スタック

### フロントエンド (`packages/web`)
- Next.js 15.4.6 (App Router使用)
- React 19.1.0
- TypeScript (strict mode)
- Tailwind CSS v4
- OpenNext.js Cloudflare対応

### バックエンド (`packages/server`)
- Hono (軽量Webフレームワーク)
- TypeScript (ESモジュール)
- Cloudflare Workers対応

## 開発コマンド

### 基本コマンド
```bash
# 依存関係インストール（プロジェクトルートで実行）
pnpm install

# フロントエンド開発サーバー起動
cd packages/web
pnpm run dev

# バックエンド開発サーバー起動
cd packages/server
pnpm run dev
```

## プロジェクト構造

```
packages/
├── web/          # Next.jsフロントエンド
│   └── src/app/  # App Router
└── server/       # Hono APIサーバー
    └── src/      # APIエンドポイント
```

## コーディング規約

### TypeScript
- strict modeを使用
- importは相対パスのみ使用する

### React/Next.js
- 関数コンポーネントのみ使用
- `export default`でエクスポート
- App Routerパターンに従う

### スタイリング
- Tailwind CSS v4のユーティリティクラスを使用
- カスタムCSSは`globals.css`に記述

### 命名規則
- コンポーネント: PascalCase
- 関数・変数: camelCase
- ファイル名: コンポーネントはPascalCase、その他はkebab-case

## 重要な注意事項

1. **モノレポ構造**: pnpmワークスペースを使用。パッケージ間の依存関係に注意
2. **Cloudflare対応**: 両パッケージともCloudflare Workersで動作するよう設計
3. **型安全性**: TypeScript strictモードが有効。型エラーがないことを確認

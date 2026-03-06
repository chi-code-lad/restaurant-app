# 開発ログ（Day1）

## 今日やったこと

### 1. Node.js 環境構築

* Node.js をインストール
* npm コマンドが使えない問題を解決
* PowerShell の ExecutionPolicy を変更して npm を実行可能にした

### 2. Next.js プロジェクト作成

* create-next-app を使用してプロジェクトを作成
* プロジェクト名：restaurant-app

### 3. Next.js 初期設定

以下の構成で作成

* TypeScript
* ESLint
* Tailwind CSS
* App Router

### 4. 開発サーバー起動

以下のコマンドでアプリを起動

```
npm run dev
```

ブラウザで確認
http://localhost:3000

Next.js の初期ページが表示されることを確認。

### 5. 開発環境確認

* VS Code でプロジェクトを開いた
* page.tsx を編集すれば画面が変わることを確認

---

## 作ろうとしているアプリ

**行きたい店共有アプリ**

### 機能（予定）

* 店を追加
* 店一覧表示
* 店詳細
* 行ったかどうか記録
* グループで共有

---

## 次やること

* Supabase 環境構築
* データベース設計
* 店一覧画面作成
* 店追加フォーム作成

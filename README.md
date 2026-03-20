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

## 今日の進捗（2026-03-21）

### Supabase設定
- Supabase プロジェクト確認
- API Keys を `.env.local` に設定
  ```env
  NEXT_PUBLIC_SUPABASE_URL=https://gnpirmjrlwxfflzyptxv.supabase.co
  NEXT_PUBLIC_SUPABASE_ANON_KEY=sb_publishable_MvXfTP7_MrH0eQlTvlR2Sg_xAJf23sf

## テーブル作成

### restaurants テーブル作成

**カラム:**

- `id` UUID, PRIMARY KEY
- `name` TEXT NOT NULL
- `gene` TEXT
- `url` TEXT
- `visited` BOOLEAN
- `repeat` BOOLEAN
- `type` TIMESTAMP DEFAULT now()

> RLS は開発用に OFF に設定

---

## フロント実装

- `lib/supabase.ts` で Supabase client 作成
- Next.js 側で「＋ 店を追加」ボタン実装
  - `useState` で1回だけ追加フラグ管理
  - `addTestData` 関数で Supabase にデータ追加
  - カラム名 `gene` に合わせてINSERT成功
- タイムスタンプはUTCのまま確認済み

---

## 成果

- ボタン押すと Supabase にテストデータが追加される
- 1回だけ追加されるようになり、無限に増える問題解消
- DB 接続と INSERT 動作を確認

---

## 次のステップ

1. Supabase から店舗データを取得して画面に一覧表示
2. 入力フォームでユーザーが店を追加できるようにする
3. 「行った / リピあり」チェック機能追加
4. 共有ユーザー管理（最大5人）

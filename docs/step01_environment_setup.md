# 第1章：開発環境構築＆GitHub・Gitの基本操作手順書（初心者向け完全版）

## この章のゴール
- 開発に必要なツール（VSCode、Java、Git）のインストールができる
- GitHubアカウントを作成できる
- GitHubリポジトリを作成・クローンし、ファイルの編集・コミット・プッシュができる

---

## 目次
1. PC準備
2. VSCodeのインストールと初期設定
3. Java(JDK)のインストール
4. Gitのインストール
5. GitHubアカウント作成
6. GitHubリポジトリ作成（選択肢の詳細解説付き）
7. VSCodeでリポジトリをクローン
8. ファイル編集・コミット・プッシュ（Gitの基本操作）
9. チェックポイント

---

## 1. PC準備
- Windows/MacどちらでもOK
- 推奨スペック：メモリ8GB以上（4GBでも可）
- インターネット接続必須

### よくある質問
- Q. スペックが足りない場合は？  
  A. 4GBでも動作はできますが、複数アプリ同時起動や大規模開発には8GB以上推奨です。

---

## 2. VSCodeのインストールと初期設定

### 手順
1. [Visual Studio Code公式サイト](https://code.visualstudio.com/)にアクセス
2. 「Download for Windows」または「Download for Mac」をクリック
3. ダウンロードしたファイル（Windowsは`.exe`、Macは`.zip`または`.dmg`）をダブルクリック
4. インストーラー画面の指示通り「Next」「Install」で進める
5. インストール完了後、VSCodeを起動

### 初期設定のおすすめ
- 日本語化：左下の地球アイコン→「Japanese Language Pack」をインストール
- 「拡張機能」アイコン（四角が4つ並んだマーク）から、  
  - 「Java Extension Pack」  
  - 「GitHub Pull Requests and Issues」などを検索して追加
- テーマやフォントサイズ変更は「設定」アイコン（左下歯車）から

### VSCodeの便利機能
- 「エクスプローラー」：ファイル構成が一目で分かる
- 「検索」：ファイル横断で文字列検索
- 「ソース管理」：Git操作が簡単
- 「ターミナル」：VSCode内でコマンド操作可能

### よくある質問
- Q. インストール後、画面が英語のままです。  
  A. 左下の地球マークから「Japanese Language Pack」を追加できます。
- Q. 拡張機能はどこで追加できますか？  
  A. 左側の四角アイコン「拡張機能」から検索・追加できます。

---

## 3. Java(JDK)のインストール

### 手順
1. [Adoptium公式サイト（Temurin）](https://adoptium.net/)にアクセス
2. 「Temurin 17 (LTS)」→「Latest release」→「.msi Installer（Windows）」または「.pkg（Mac）」を選択
3. ダウンロードしたファイルをダブルクリックで実行
4. インストーラーの指示に従い「Next」「Install」
5. インストール完了後、「Finish」で閉じる

### インストール後の確認
- コマンドプロンプト（Windows）やターミナル（Mac）で  
  `java -version`
- 例：  
  ```
  openjdk version "17.0.10" 2024-01-16
  ```

### よくある質問
- Q. `java -version` でエラーが出る  
  A. インストールが失敗しているか、パス（環境変数）の設定が必要です。  
    Javaのインストール先フォルダを「Path」に追加し、PC再起動してください。

---

## 4. Gitのインストール

### 手順
1. [Git公式サイト](https://git-scm.com/)にアクセス
2. 「Download for Windows」またはMac版をクリック
3. ダウンロードしたファイルをダブルクリックで実行
4. インストーラーの指示通り進める（基本はデフォルトでOK）

#### インストール時の注意
- 「PATH環境変数」の設定だけ、「Use Git from the command line and also from 3rd-party software」を選択（デフォルト）
- その他は変更不要です

### インストール後の確認
- コマンドプロンプトやターミナルで  
  `git --version`

### よくある質問
- Q. インストール中の選択肢が多くて不安です  
  A. 基本は「Next」で問題ありません。上記の「PATH」だけ注意すればOKです。

---

## 5. GitHubアカウント作成

### 手順
1. [GitHub公式サイト](https://github.com/)にアクセス
2. 「Sign up」をクリック
3. メールアドレス、パスワード、ユーザー名を入力
4. 認証メールを受け取り、メール内リンクをクリックして認証

### よくある質問
- Q. ユーザー名は何でもいい？  
  A. 覚えやすく、英字・数字・記号（-）のみが使えます。

---

## 6. GitHubリポジトリ作成（選択肢の詳細解説付き）

### 手順
1. GitHub右上の「＋」→「New repository」
2. 下記項目を入力・選択

| 項目 | 意味・役割 | 初心者向けおすすめ |
| --- | --- | --- |
| Repository name | プロジェクト名 | 分かりやすい名前を入力 |
| Description | プロジェクト説明（任意） | 簡単な説明を記載 |
| Public/Private | 公開/非公開 | 学習用途なら「Public」がおすすめ |
| README.md | プロジェクト説明ファイル | 必ず作成（チェック推奨） |
| .gitignore | 管理しないファイル指定 | 「Java」を選択（推奨） |
| License | 利用規約 | 学習なら「None」でもOK |

### 各選択肢の意味
- **README.md**：プロジェクト説明。最初から作成推奨
- **.gitignore**：不要ファイル除外。Javaの場合「Java」を選ぶ
- **License**：公開範囲明記。迷ったら「None」でOK

### よくある質問
- Q. 選択しなかった項目は後から追加できる？  
  A. README.md、.gitignore、Licenseは後から追加・変更可能です。

---

## 7. VSCodeでリポジトリをクローン

### 手順
1. GitHubリポジトリページで「Code」→「HTTPS」URLをコピー
2. VSCodeを開く
3. 左側「ソース管理」アイコン（三つの丸が線で繋がったマーク）をクリック  
　（サイドバーが非表示の場合は「表示」→「サイドバーの表示」）
4. 「クローン」ボタン→コピーしたURLを貼り付け
5. 保存場所を選択し、「開く」をクリック

### よくある質問
- Q. 「ソース管理」アイコンが見つからない  
  A. 左側サイドバーの下から2～4番目の丸マーク。ショートカット「Ctrl + Shift + G」（Win）、「Cmd + Shift + G」（Mac）でも開けます。

---

## 8. ファイル編集・コミット・プッシュ（Gitの基本操作）

### 手順
1. VSCodeで`README.md`などを編集・保存
2. 左側「ソース管理」アイコンをクリック
3. 「変更」一覧に編集ファイルが表示される
4. ファイル名左「＋」をクリック（ステージ）
5. 上部「コミットメッセージ」欄に変更内容を入力  
　例：`README.mdに自己紹介を追加`
6. 「✔」ボタンでコミット
7. 「sync changes」ボタンが出たらクリック（GitHubとローカルを同期）
8. GitHubのWeb画面で変更反映を確認

### 補足
- 「sync changes」＝変更の同期。コミット内容をGitHubへ反映
- 「Would you like Visual Studio Code to periodically run 'git fetch'?」は「Yes」でOK（最新状態自動取得）

### よくある質問
- Q. 「make sure you configure your user.name and user.email in git」と出てコミットできない  
  A. 下記コマンドでユーザー情報を設定  
    ```
    git config --global user.name "あなたの名前"
    git config --global user.email "あなたのメールアドレス"
    ```
- Q. コミットメッセージは何を書けばいい？  
  A. 何を変更したかを簡潔に（例：`初回コミット`、`README.mdに自己紹介追加`）

---

## 9. チェックポイント

- [ ] VSCodeを起動できた
- [ ] JavaとGitがコマンドでバージョン確認できた
- [ ] GitHubアカウントを作成できた
- [ ] リポジトリを作成できた（README.md, .gitignore有り）
- [ ] VSCodeでリポジトリをクローンできた
- [ ] ソース管理アイコンの場所が分かった
- [ ] ファイル編集→コミット→GitHubへプッシュできた
- [ ] 「sync changes」「git fetch」も理解できた
- [ ] コミット時のエラーも解決できた

---

## 次のステップ

- Spring Bootプロジェクトの作成
- Javaアプリの実行
- GitHubでバージョン管理を継続

---

### フィードバック・質問歓迎！

つまずいたポイントや、分かりづらい箇所があれば、ぜひ教えてください。  
手順書に随時反映して、より分かりやすくしていきます。

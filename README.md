# 拡張アラームクロックアプリ

Android公式AOSP（Android Open Source Project）の DeskClock アプリを拡張したアラームクロックアプリです。

## プロジェクトの概要

このプロジェクトは、Android公式の時計アプリ（DeskClock）をベースに、カスタム機能を追加した拡張版アプリを作成することを目的としています。

## 現在の状況

### ✅ 完了済み
- [x] AOSP DeskClock アプリのソースコードを取得
- [x] プロジェクトのGit管理を設定
- [x] 基本的なプロジェクト構造の確認
- [x] `.gitignore` ファイルの設定

### 🔄 現在の構造

```
alarm_extention/
├── AndroidManifest.xml          # アプリマニフェスト
├── Android.bp                   # ビルド設定
├── src/                         # Kotlinソースコード
│   └── com/android/deskclock/
│       ├── DeskClock.kt         # メインアクティビティ
│       ├── alarms/              # アラーム関連
│       ├── timer/               # タイマー関連
│       ├── stopwatch/           # ストップウォッチ関連
│       └── worldclock/          # 世界時計関連
├── res/                         # リソースファイル
│   ├── layout/                  # レイアウト
│   ├── values/                  # 文字列、色、スタイル
│   └── drawable/                # 画像リソース
└── tests/                       # テストコード
```

## 主要機能

### 現在の機能 (AOSP DeskClock)
- ⏰ **アラーム** - 複数のアラーム設定、スヌーズ機能
- 🌍 **世界時計** - 複数のタイムゾーン表示
- ⏱️ **タイマー** - カウントダウンタイマー
- ⏲️ **ストップウォッチ** - ラップタイム機能付き
- 🔧 **ウィジェット** - アナログ・デジタル時計ウィジェット
- 🌙 **スクリーンセーバー** - 時計表示機能

### 技術仕様
- **最小SDK**: 23 (Android 6.0)
- **ターゲットSDK**: 30 (Android 11)
- **言語**: Kotlin
- **アーキテクチャ**: Fragment-based with ViewPager
- **ライブラリ**: AndroidX, Material Design Components

## 開発環境

### 必要な環境
- Android Studio (Arctic Fox 以降推奨)
- Android SDK (API 23以降)
- Kotlin サポート
- Git

### 🔧 セットアップ手順

#### 1. GitHubリポジトリの設定
```bash
# 1. GitHubで新しいリポジトリを作成
# 2. リモートリポジトリを追加
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git

# 3. 最初のプッシュ
git push -u origin main
```

#### 2. Android Studioでのプロジェクト開発
1. **プロジェクトを開く**
   - Android Studio を起動
   - 「Open an existing Android Studio project」を選択
   - プロジェクトのルートディレクトリ（`alarm_extention`）を選択

2. **初回同期**
   - Android Studio が自動的に Gradle 同期を開始
   - 必要な SDK とライブラリが自動でダウンロードされます

3. **ビルドと実行**
   ```bash
   # コマンドラインから
   ./gradlew assembleDebug
   
   # または Android Studio の「Build > Make Project」
   ```

### 🎯 Android Studio での作業流れ
1. **コード編集**: `src/` ディレクトリ内のKotlinファイルを編集
2. **リソース編集**: `res/` ディレクトリ内のレイアウトやリソースを編集
3. **ビルド**: `Build > Make Project` でプロジェクトをビルド
4. **実行**: エミュレータまたは実機で実行
5. **デバッグ**: Android Studio のデバッガーを使用

### 🔄 Git ワークフロー
```bash
# 1. 機能開発
git checkout -b feature/new-feature
# コードを編集...

# 2. コミット
git add .
git commit -m "Add new feature"

# 3. プッシュ
git push origin feature/new-feature

# 4. メインブランチにマージ
git checkout main
git merge feature/new-feature
git push origin main
```

## 次のステップ

### 📋 計画中の拡張機能
- [ ] カスタムアラーム音の追加
- [ ] 天気情報の統合
- [ ] 睡眠パターンの追跡
- [ ] カスタムテーマ機能
- [ ] 拡張通知機能

## コード品質

このプロジェクトは、Android公式のソースコードをベースにしているため、以下の品質が保証されています：

- ✅ **アーキテクチャ**: 綺麗で保守性の高い設計パターン
- ✅ **パフォーマンス**: 最適化されたレンダリングとメモリ使用量
- ✅ **アクセシビリティ**: 障害者対応機能を含む
- ✅ **国際化**: 多言語サポート
- ✅ **テスト**: 包括的なテストスイート

### 🔧 トラブルシューティング

#### Android Studio でよくある問題
1. **Gradle 同期エラー**
   ```bash
   # Gradle キャッシュをクリア
   ./gradlew clean
   
   # Android Studio で File > Invalidate Caches and Restart
   ```

2. **SDK not found エラー**
   - Android Studio の SDK Manager で必要な SDK をインストール
   - `local.properties` ファイルで SDK パスを確認

3. **メモリ不足エラー**
   - `gradle.properties` で JVM メモリを増やす:
   ```properties
   org.gradle.jvmargs=-Xmx4096m -Dfile.encoding=UTF-8
   ```

#### Git 関連の問題
1. **プッシュ権限エラー**
   ```bash
   # SSH キーを設定、または HTTPS で認証
   git remote set-url origin git@github.com:USERNAME/REPOSITORY.git
   ```

2. **コンフリクト解決**
   ```bash
   # コンフリクトファイルを手動で編集後
   git add .
   git commit -m "Resolve merge conflicts"
   ```

## コミット履歴

```
0989082 - Convert AOSP project to Android Studio Gradle project
a6ff633 - Update .gitignore to exclude IDE configuration files
a604b41 - Initial commit: Add AOSP DeskClock app source code
```

## ライセンス

このプロジェクトは、Apache License 2.0 のもとで提供されています。
詳細は、各ソースファイルのヘッダーをご確認ください。

---

**注意**: このプロジェクトはAOSP DeskClockアプリを拡張したものです。オリジナルのコードは参考目的で提供されており、積極的にサポートされていません。 
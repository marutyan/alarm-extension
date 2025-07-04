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
- Android Studio
- Android SDK
- Kotlin サポート

### ビルド
```bash
# Android Studio でプロジェクトを開く
# または
./gradlew assembleDebug
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

## コミット履歴

```
a6ff633 - Update .gitignore to exclude IDE configuration files
a604b41 - Initial commit: Add AOSP DeskClock app source code
```

## ライセンス

このプロジェクトは、Apache License 2.0 のもとで提供されています。
詳細は、各ソースファイルのヘッダーをご確認ください。

---

**注意**: このプロジェクトはAOSP DeskClockアプリを拡張したものです。オリジナルのコードは参考目的で提供されており、積極的にサポートされていません。 
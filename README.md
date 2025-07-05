# 🤖 AI プロンプト管理ファイル自動生成ツール

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live-green)](https://your-username.github.io/prompt-file-generator/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow.svg)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

GitHub プロンプト管理システム対応の自動ファイル生成ツール。新しいプロンプトから必要なファイル一式を自動生成し、GitHubに直接アップロードできます。

## ✨ 主な機能

### 📝 自動ファイル生成
- **metadata.yml** - プロンプトのメタデータ（推定トークン数も自動計算）
- **prompt.md** - 実際のプロンプト内容
- **README.md** - プロンプトの説明書
- **examples.md** - 使用例のテンプレート
- **versions/v1.0.md** - バージョン管理用初期ファイル

### 🚀 GitHub連携
- **直接アップロード** - GitHub APIを使用してワンクリックでアップロード
- **既存ファイル更新** - SHA自動取得による安全な更新
- **進捗表示** - リアルタイムアップロード状況
- **エラーハンドリング** - 詳細なエラーメッセージと解決方法

### 💻 ユーザビリティ
- **レスポンシブデザイン** - PC・スマートフォン対応
- **タグ管理** - 動的なタグ追加・削除
- **プレビュー機能** - 生成されたファイルをタブで確認
- **ワンクリックコピー** - 各ファイルを個別コピー
- **一括ダウンロード** - 全ファイルを ZIP でダウンロード

## 🌐 デモ

**ライブデモ**: [https://your-username.github.io/prompt-file-generator/](https://your-username.github.io/prompt-file-generator/)

## 🚀 クイックスタート

### 1. 基本的な使用方法

1. **プロンプト情報の入力**
   ```
   プロンプトタイトル: ブログ記事作成アシスタント
   カテゴリ: writing
   タグ: blog, SEO, content
   概要: SEO対策済みのブログ記事を自動生成
   ```

2. **ファイル生成**
   - 「📁 ファイル一式を生成」をクリック
   - 各タブで生成されたファイルを確認

3. **ファイルの活用**
   - 個別コピーまたは一括ダウンロード
   - GitHubの `prompts/[prompt-id]/` フォルダに配置

### 2. GitHub直接アップロード

#### 初期設定

1. **Personal Access Token の作成**
   - [GitHub Settings → Tokens](https://github.com/settings/tokens)
   - 「Generate new token (classic)」
   - スコープ: `repo` を選択
   - トークンをコピー

2. **ツールでの設定**
   ```
   Personal Access Token: ghp_xxxxxxxxxxxx
   リポジトリ: your-username/prompt-library
   ブランチ名: main
   ```

#### 使用方法

1. プロンプト情報を入力
2. GitHub設定を入力（初回のみ）
3. 「🚀 GitHubに直接アップロード」をクリック
4. 完了！自動的にGitHubにアップロード

## 📁 ファイル構造

生成されるファイル構造：

```
prompts/[prompt-id]/
├── metadata.yml          # プロンプトのメタデータ
├── README.md            # プロンプトの説明書  
├── prompt.md            # 実際のプロンプト内容
├── examples.md          # 使用例
└── versions/
    └── v1.0.md         # 初期バージョン
```

### metadata.yml の例

```yaml
id: "blog-writer-assistant"
title: "ブログ記事作成アシスタント"
category: "writing"
tags: ["blog", "SEO", "content"]
version: "1.0"
created: "2024-07-06"
updated: "2024-07-06"
author: "your-name"
model_tested: ["claude-4"]
difficulty: "intermediate"
estimated_tokens: 250
description: "SEO対策済みのブログ記事を自動生成するプロンプト"
```

## 🔧 セットアップ

### ローカル環境での実行

1. **リポジトリのクローン**
   ```bash
   git clone https://github.com/your-username/prompt-file-generator.git
   cd prompt-file-generator
   ```

2. **ローカルサーバーの起動**
   ```bash
   # Python を使用する場合
   python -m http.server 8000
   
   # Node.js を使用する場合  
   npx serve .
   
   # または単純にHTMLファイルをブラウザで開く
   open index.html
   ```

3. **ブラウザでアクセス**
   ```
   http://localhost:8000
   ```

### GitHub Pages での公開

1. **リポジトリ設定**
   - Settings → Pages
   - Source: Deploy from a branch
   - Branch: main / (root)

2. **アクセスURL**
   ```
   https://your-username.github.io/prompt-file-generator/
   ```

## 📋 プロンプト管理システムとの連携

このツールは [AI プロンプト管理システム](https://github.com/your-username/prompt-library) と完全に連携しています。

### 推奨ワークフロー

```mermaid
graph LR
    A[プロンプトアイデア] --> B[生成ツール]
    B --> C[ファイル生成]
    C --> D[GitHub アップロード]
    D --> E[プロンプトライブラリ]
    E --> F[チーム共有]
```

### 管理システムの構造

```
prompt-library/
├── categories/              # カテゴリ別分類
│   ├── coding/
│   ├── writing/
│   ├── analysis/
│   └── creative/
├── prompts/                # このツールで生成したファイル
│   └── [prompt-id]/
└── templates/              # テンプレート
```

## 🛠️ カスタマイズ

### デフォルト値の変更

```javascript
// 作成者名のデフォルト値
document.getElementById('author').value = 'Your Name';

// 新しいカテゴリの追加
const categorySelect = document.getElementById('category');
const newOption = document.createElement('option');
newOption.value = 'business';
newOption.textContent = 'business';
categorySelect.appendChild(newOption);
```

### スタイルの変更

```css
/* テーマカラーの変更 */
:root {
    --primary-color: #667eea;
    --secondary-color: #764ba2;
}

/* 会社ロゴの追加 */
.header::before {
    content: url('path/to/logo.png');
    display: block;
    margin-bottom: 20px;
}
```

## 🔒 セキュリティ

### Personal Access Token の管理

- ✅ **ローカル保存されません** - トークンはブラウザセッションのみ
- ✅ **HTTPS通信** - 全ての通信は暗号化
- ✅ **最小権限** - 必要最小限のスコープ（repo）のみ
- ⚠️ **共有PCでの注意** - 使用後はブラウザをクリア

### 推奨セキュリティ設定

```bash
# Tokenの有効期限を設定（30日など）
# 定期的なTokenの更新
# 使用しないTokenの無効化
```

## 🐛 トラブルシューティング

### よくある問題と解決方法

#### ❌ GitHub アップロードエラー

**401 Unauthorized**
```
原因: Personal Access Tokenが無効
解決: 新しいTokenを生成して再設定
```

**404 Not Found**
```
原因: リポジトリ名が間違っている
解決: username/repository-name の形式を確認
```

**403 Forbidden**
```
原因: Tokenに適切な権限がない
解決: Token作成時に「repo」スコープを選択
```

#### ❌ ファイル生成エラー

**空のファイルが生成される**
```
原因: 必須フィールドが未入力
解決: 全ての必須項目を入力
```

**日本語が文字化けする**
```
原因: 文字エンコーディングの問題
解決: ブラウザの文字エンコーディングをUTF-8に設定
```

### デバッグ方法

```javascript
// ブラウザの開発者ツールでエラー確認
console.log(generatedFiles);

// GitHub API レスポンスの確認
console.log(response.status, response.statusText);
```

## 📊 使用統計

### パフォーマンス
- ⚡ **ファイル生成**: < 100ms
- 🚀 **GitHub アップロード**: 2-5秒（5ファイル）
- 💾 **メモリ使用量**: < 10MB

### 対応ブラウザ
- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+

## 🤝 コントリビューション

### 改善提案・バグ報告

1. **Issue の作成**
   - [Issues ページ](https://github.com/your-username/prompt-file-generator/issues)
   - バグ報告または機能提案のテンプレートを使用

2. **Pull Request**
   ```bash
   git fork
   git checkout -b feature/new-feature
   git commit -m "Add new feature"
   git push origin feature/new-feature
   ```

### 開発ガイドライン

- **コードスタイル**: Prettier + ESLint
- **コミットメッセージ**: Conventional Commits
- **テスト**: 手動テスト + ブラウザ互換性確認

## 🎯 ロードマップ

### Phase 2 (予定)
- [ ] プレビュー機能（Markdownレンダリング）
- [ ] テンプレート保存機能
- [ ] インポート機能（既存プロンプトの編集）
- [ ] バリデーション強化

### Phase 3 (構想)
- [ ] AI支援（プロンプト改善提案）
- [ ] 分析機能（使用統計）
- [ ] チーム機能（複数人での共同編集）
- [ ] プラグインシステム

## 📄 ライセンス

MIT License - 詳細は [LICENSE](LICENSE) ファイルを参照

## 🙏 謝辞

- [GitHub API](https://docs.github.com/en/rest) - ファイルアップロード機能
- [Font Awesome](https://fontawesome.com/) - アイコン
- [Prettier](https://prettier.io/) - コードフォーマット

## 📞 サポート

- **Issues**: [GitHub Issues](https://github.com/your-username/prompt-file-generator/issues)
- **Discussions**: [GitHub Discussions](https://github.com/your-username/prompt-file-generator/discussions)
- **Email**: your-email@example.com

---

**🌟 このツールが役に立った場合は、ぜひ Star をお願いします！**

[![Star this repository](https://img.shields.io/github/stars/your-username/prompt-file-generator?style=social)](https://github.com/your-username/prompt-file-generator/stargazers)

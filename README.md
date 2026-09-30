# Python Project Template

`uv` と `Ruff` を使用した Python プロジェクトのスターターテンプレートです。AIエージェント（Antigravity等）との協調開発に最適化されたガイドラインとカスタムスキルを同梱しています。

## 🚀 特徴

- **高速なパッケージ管理**: `uv` による高速な依存関係解決と仮想環境管理
- **高速なリンター & フォーマッタ**: `Ruff` による統一されたコードスタイルと品質チェック
- **テスト自動化**: `pytest` 設定済み
- **VS Code 連携**: 保存時の Ruff 自動フォーマット & インポート整理が設定済み
- **AI エージェント行動規範**: 開発方針やコーディング規約を定めた [`AGENTS.md`](./AGENTS.md) を同梱
- **エージェントスキル同梱**: Gitコミット自動作成 (`auto-commit`) や README 自動更新 (`write-readme`) スキルをビルトイン

## 🛠️ 技術スタック

- **Python**: `>= 3.13`
- **パッケージ・環境管理**: [uv](https://github.com/astral-sh/uv)
- **リンター / フォーマッタ**: [Ruff](https://github.com/astral-sh/ruff)
- **テストフレームワーク**: [pytest](https://docs.pytest.org/)
- **AI 支援**: Antigravity / Gemini 等のエージェント向け開発規範 & スキル構成

---

## 📋 使い方

### 1. テンプレートから新規プロジェクトを作成

このテンプレートからプロジェクトを作成したら、まず `pyproject.toml` 内のプレースホルダーを実際のプロジェクト情報に書き換えてください。

`pyproject.toml`:

```toml
[project]
name = "your-project-name"        # {{PROJECT_NAME}} を書き換え
version = "0.1.0"
description = "Your description"  # {{PROJECT_DESCRIPTION}} を書き換え
```

### 2. 環境構築

`uv` を使用して依存関係を同期し、仮想環境を自動生成します。

```bash
uv sync
```

### 3. 環境変数の設定 (必要に応じて)

環境変数が必要なプロジェクトの場合は、`.env.example` をコピーして `.env` を作成します。

```bash
cp .env.example .env
```

---

## 💻 開発用コマンド

### パッケージの追加・削除

```bash
# 通常の依存関係を追加
uv add <package_name>

# 開発用依存関係を追加
uv add --dev <package_name>

# パッケージの削除
uv remove <package_name>
```

### リンター & フォーマッタ (Ruff)

```bash
# コードの自動フォーマット
uv run ruff format .

# リンターチェック (静的解析)
uv run ruff check .

# リンターの自動修正
uv run ruff check --fix .
```

### テストの実行 (pytest)

```bash
uv run pytest
```

---

## 🤖 AIエージェントとの開発

本テンプレートには、AIコーディングアシスタントとの効率的なペアプログラミングを実現するための設定が組み込まれています。

- **[`AGENTS.md`](./AGENTS.md)**: コーディング規約（型ヒント、GoogleスタイルDocstring、エラーハンドリング等）や意思決定の優先順位を定めた規範ファイルです。
- **同梱スキル (`.agents/skills/`)**:
  - `auto-commit`: 作業ツリーの差分を解析し、適切なコミットメッセージでコミットを作成・分割します。
  - `write-readme`: プロジェクト構成やソースコードを解析し、最新状態に合わせた `README.md` を生成・更新します。

---

## 📂 ディレクトリ構成

```text
.
├── .agents/
│   └── skills/                  # AIエージェント用カスタムスキル
│       ├── auto-commit/         # コミット自動作成スキル
│       └── write-readme/        # README自動生成・更新スキル
├── .vscode/
│   ├── extensions.json          # VS Code 推奨拡張機能
│   └── settings.json            # VS Code 保存時自動フォーマット設定
├── tests/
│   └── conftest.py              # pytest 用共通設定
├── .env.example                 # 環境変数設定サンプル
├── .gitignore
├── .python-version              # Python バージョン指定 (3.13)
├── AGENTS.md                    # AIエージェントの行動規範・コーディング規約
├── pyproject.toml               # プロジェクト定義 & Ruff / pytest 設定
├── README.md                    # 本ドキュメント
└── uv.lock                      # uv ロックファイル
```

---

## 👤 Author

- **プロジェクト作成者**: [muetaek0321](https://github.com/muetaek0321)
- **README 作成**: Gemini 3.8 Flash

# ☁️ OCI Serverless Fun

このリポジトリは、**Oracle Cloud Infrastructure (OCI)** 上で動作する  
サーバレスアプリケーションのサンプル構成です。  

- **FrontEnd**：Vue 3 + Vite によるフロントエンド  
- **BackEnd**：OCI Functions (Python) によるサーバレス API  

## 🧩 Repository Structure
OCI-servlesss-fun/
├── FrontEnd/ # Vue.js + Vite アプリ
└── Backend/ # OCI Functions (Python)

## ⚙️ FrontEnd Setup

フロントエンドは **Vite + Vue 3** を使用しています。  
ローカルでの開発・ビルド・デプロイ手順は以下の通りです。

### 🧱 Project Setup
依存関係のインストール：
```bash
npm install
```
ローカル開発サーバーの起動：
```bash
npm run dev
```
本番ビルドの作成：

```bash
npm run build
```
🐍 BackEnd Setup

バックエンドは OCI Functions (Python 3.11) をベースにしています。
各フォルダが独立した関数としてデプロイされます。

📁 Directory Structure
Backend/
├── add-tasks/
│   ├── func.py
│   └── func.yaml
├── delete-tasks/
│   ├── func.py
│   └── func.yaml
├── edit-tasks/
│   ├── func.py
│   └── func.yaml
└── list-tasks/
    ├── func.py
    └── func.yaml

🚢 Deploy to OCI

各 Function ディレクトリで以下のコマンドを実行してデプロイします。

cd Backend/add-tasks
fn deploy --app task-app

cd ../delete-tasks
fn deploy --app task-app

cd ../edit-tasks
fn deploy --app task-app

cd ../list-tasks
fn deploy --app task-app

🔍 Test Locally

ローカル環境で関数を呼び出す場合：

fn invoke task-app add-tasks

# 第1回: オリエンテーションと環境構築

## 1. カリキュラムの説明と学習のゴール設定

### カリキュラムの概要
- **目的**: SQLiteを使用したデータ操作とStreamlitでのアプリケーション開発を通じて、データ活用スキルを習得する。
- **ゴール**:
  - Python、SQLite、Streamlitの基礎を理解する。
  - 簡単なデータ管理アプリケーションを構築できるようになる。
  
### 学習の流れ
1. **オリエンテーションと環境構築**（今回の講義）
2. **SQLiteを使用したデータ管理**
3. **Streamlitを使ったデータ可視化アプリの構築**
4. **最終プロジェクト: データ管理と可視化アプリの作成**

---

## 2. Python、SQLite、Streamlitの開発環境のセットアップ

### Pythonのインストール
- **Python 3.10以上を推奨**（既にインストール済みの場合はスキップ）

#### コマンド
```bash
# Pythonのインストール確認
python --version

# Poetryを使用する場合のインストール
pip install poetry
```

### SQLiteのインストール
- SQLiteはPythonに組み込まれているため、別途インストール不要。

#### 動作確認
```python
# 簡単なSQLiteの動作確認
import sqlite3

# メモリ上にデータベースを作成
connection = sqlite3.connect(":memory:")
cursor = connection.cursor()

# テーブル作成
cursor.execute("CREATE TABLE users (id INTEGER PRIMARY KEY, name TEXT)")
cursor.execute("INSERT INTO users (name) VALUES ('Alice')")
connection.commit()

# データ取得
cursor.execute("SELECT * FROM users")
print(cursor.fetchall())  # 出力: [(1, 'Alice')]
```

### Streamlitのセットアップ
- **Streamlitのインストール**

#### コマンド
```bash
# Streamlitのインストール
pip install streamlit

# インストール後の確認（サンプルアプリの実行）
streamlit hello
```

---

## 3. 開発環境の確認（インストールと基本的な動作テスト）

### Pythonの動作確認
- **Pythonバージョンの確認**

#### コマンド
```bash
python --version  # 出力例: Python 3.10.4
```

- **簡単なスクリプトの実行**

#### コード
```python
print("Hello, Python!")  # 出力: Hello, Python!
```

### SQLiteの動作確認
- **データベース作成と基本的なクエリの実行**

#### コマンド
```python
import sqlite3

connection = sqlite3.connect("test.db")
cursor = connection.cursor()

# テーブルの作成
cursor.execute("CREATE TABLE IF NOT EXISTS books (id INTEGER PRIMARY KEY, title TEXT)")
cursor.execute("INSERT INTO books (title) VALUES ('Python for Beginners')")
connection.commit()

# データの取得
cursor.execute("SELECT * FROM books")
print(cursor.fetchall())  # 出力: [(1, 'Python for Beginners')]
```

### Streamlitの動作確認
- **簡単なStreamlitアプリの作成と実行**

#### コード (`app.py`)
```python
import streamlit as st

st.title("環境構築の確認")
st.write("このページは、Streamlitが正常に動作しているかを確認するためのものです。")
st.button("クリックしてください")
```

#### コマンド
```bash
# アプリの実行
streamlit run app.py
```
 

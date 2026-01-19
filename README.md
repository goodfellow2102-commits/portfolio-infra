## ubuntu-db 構築

### 環境
- 仮想化：VirtualBox
- OS：Ubuntu 22.04
- VM名：ubuntu-db
- ネットワーク：Host-Only Adapter
- IPアドレス：192.168.56.103

### 実施内容
- Ubuntu 22.04 インストール
- SSH（Rlogin）接続設定
- sudo権限付与
- ネットワーク疎通確認
- MySQL Server インストール
- MySQL サービス起動確認

### Ubuntu初期設定で苦戦した点
- GUIからターミナルが起動できない事象が発生
- SSH接続に切り替えて作業を継続
- 初期ユーザーにsudo権限がなく管理操作が不可
- sudoグループへ追加して解決
- キーボード設定により入力補助ダイアログが頻繁に表示された

### MySQL構築時のトラブル
- apt update 実行時に GPG署名エラー(EXPKEYSIG)が発生
- MySQL公式リポジトリの署名鍵期限切れが原因
- curl未導入により鍵取得に失敗
- curl導入後、GPG鍵を再登録して解消

### 動作確認
結果：
- active (running) を確認

### 現在の状態
- MySQLサーバは正常稼働中
- 外部接続は未設定
- 次回、Webサーバ（ubuntu-web）からの接続検証を予定
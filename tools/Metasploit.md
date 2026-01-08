# Metasploit

## 何のツール？

侵入テストをサポートするツールで情報収集、スキャン、エクスプロイトのツールが含まれる

## 用語・前提
exploit = 脆弱性を利用して、意図しない動作を起こさせること

## 構成 / 仕組み
```text
Metasploit Framework
├─ msfconsole   ← 操作用UI
├─ modules      ← 中核（攻撃ロジック）
│   ├─ exploit
│   ├─ payload
│   ├─ auxiliary
│   └─ post
└─ tools        ← 補助ツール（単体実行）
```
- module = フレームワーク内部の部品
- tool = フレームワークに付属する独立ツール

### module
Metasploit Frameworkの中心となる攻撃ロジック。
- exploit
  - 脆弱性をつく
  - 攻撃の入り口
- payload
  - exploit成功後に実行される処理  
  - shell取得、meterpreterなど
- auxiliary
  - 補助的な機能  
  - スキャン、ブルートフォース、列挙などに使用
- post
  - 侵入後に使うモジュール  
  - 権限昇格、情報収集など

## 使い方（基本）

- root@ip-10-10-220-191:~# msfconsole 
で起動
- search ・・　でmoduleを検索
- use moduleでモジュールを操作
- moduleに対しset RHOSTS 10.10.xxなどを設定
(show optionsで確認)
- 設定後「exploit」で実行
- 成功するとsessionが確立される
- session -i でセッションと対話が可能

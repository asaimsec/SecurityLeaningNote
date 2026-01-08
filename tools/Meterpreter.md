## 何のツール？

Metasploitのpayloadの一つで、侵入後に動く高性能なシェル

## 用語・前提
Payloadには Meterpreter 以外にも、単純な shell、コマンド実行、PowerShell や Python ベースのものなど複数の種類が存在し、状況に応じて使い分ける必要がある。

## 構成 / 仕組み
```text
modules/
├─ exploit/      ← 脆弱性を突く
├─ payload/
│   └─ meterpreter/  ← ここ！
├─ post/         ← meterpreterを使う
└─ auxiliary/
```
## 使い方（基本）
```
meterpreter > hashdump
```
SAM(セキュリティアカウントマネージャ)の内容を一覧表示。WindowsのパスがNTLM形式で保存されており、解析すれば平文パスワードが検索可能な場合がある
```
meterpreter > search -f flag2.txt
```
対象ファイルを検索
```
meterpreter > shell
```
ターゲットシステム上で通常のコマンドラインシェルを起動
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
│   └─ post
└─ tools        ← 補助ツール（単体実行）
```

## 使い方（基本）


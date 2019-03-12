## mysql-expain
### explainで出力されるカラム
* id/select_type
* table
* type
* possibl_keys
* key
* key_len
* ref
* rows
* Extra

### id/select_type
* select_typeはクエリの種類を表す
* 種類はJOIN,サブクエリ,UNION及びそれらの組み合わせで決まる
#### JOINの場合
* mysqlの実行できるJOINの種類はNested Look Joinしかない(テーブルを一つずつ処理する方式)
* クエリがJOINだけの場合、SIMPLE
#### サブクエリの場合
* typeが5種類ある
	* PRIMARY
	外部クエリ
	* SUBQUERY
	相関関係のないサブクエリ  
	サブクエリが実行されるのは最初の一回だけで以降はキャッシュ
	* DEPENDENT SUBQUERY
	相関関係のあるサブクエリ
	* UNCACHEABLE SUBQUERY
	実行するたびに結果が変わる可能性のあるサブクエリ
	* DERIVED
	FROM句で用いられているクエリ
#### UNIONの場合
* 5種類のタイプが有る
	* PRIMARY
		UNIONにおいて最初にフェッチされるテーブル
	* UNION
		2番目以降にフェッチされるテーブル
	* UNION RESULT
		UNIONの実行結果
	* DEPENDENT UNION
		DEPENDENT SUBQUERYがUNION担っている場合
	* UNCACHEABLE UNION
		UNCACHEABLE SUBQUERYがUNION担っている場合

### type
* レコードアクセスタイプとも呼ばれる
* 対象のテーブルに対してどのような方法でアクセスするかを示す（重要）
	* const  
		PRIMARY_KEYまたはUNIQUEインデックスのルックアップによるアクセス。最速
	* eq_ref  
		JOINにおいてPRIMARY KEYまたはUNIQUE KYEが利用される時のアクセスタイプ
	* ref  
		ユニーク( PRIMARY or UNIQUE)ではないインデックスを使って等価検索を行った時に使われるアクセスタイプ
	* range  
		インデックスを用いた範囲検索
	* index  
		フルインデックススキャン。とても遅い
	* all  
		フルテーブルスキャン。

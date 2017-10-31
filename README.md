# MariaDB Columnstore用 HammerDB TPC-H実行スクリプト

ColumnStore にて TPC-H クエリ実行エラーに対応
Query2,5,17,19 を書き換え

| Query #         | Error           |
| --------------- |---------------|
| Query 2 | ERROR 1815 (HY000): Internal error: IDB-3012: Scalar filter and semi join are not from the same pair of tables. |
| Query 5 | ERROR 1815 (HY000): Internal error: IDB-1003: Circular joins are not supported. |
| Query 17 | ERROR 1815 (HY000): Internal error: IDB-3012: Scalar filter and semi join are not from the same pair of tables. |
| Query 19 | ERROR 1815 (HY000): Internal error: IDB-1000: 'lineitem' and 'part' are not joined. |

## Usage

MariaDB/hammerdb/hdb_tpch.tcl を HammerDBインストールディレクトリ配下の hdb_tpch.tcl と差し替える

なお、ColumnStoreに対するTPC-H　データベース作成エラーには未対応。
一旦InnoDBでデータベース作成後、手動でColumnStore用データベースを作成すること。


### HammerDB download

<http://www.hammerdb.com/download.html>

対応するHammerDB Version は 2.23

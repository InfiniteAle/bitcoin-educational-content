---
term: ロック（.LOCK）
---
Bitcoin Core でデータディレクトリをロックするために使用されるファイル。これは bitcoind または Bitcoin-qt が起動するときに作成され、ソフトウェアの複数のインスタンスが同じデータディレクトリに同時にアクセスするのを防ぐ。コンフリクトやデータの破損を防ぐことが目的です。ソフトウェアが予期せず停止した場合、.lock ファイルは残る可能性があり、Bitcoin Core を再起動する前に手動で削除する必要があります。
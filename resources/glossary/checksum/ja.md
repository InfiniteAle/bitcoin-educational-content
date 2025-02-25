---
term: チェッカム
---
チェックサムとは、データセットから計算される値のことで、データの送信中や保存中に、そのデータの完全性と妥当性を検証するために使用される。チェックサムアルゴリズムは、送信エラーやファイルの破損など、データの偶発的なエラーや意図しない変更を検出するために設計されている。チェックサムアルゴリズムには、パリティチェック、モジュラーチェックサム、暗号ハッシュ関数、BCHコード（*Bose, Ray-Chaudhuri, and Hocquenghem*）など、さまざまな種類がある。

ビットコインでは、受信アドレスの完全性を保証するためにアプリケーションレベルでチェックサムが使用される。チェックサムは、ユーザーのアドレスのペイロードから計算され、入力中に起こり得るエラーを検出するためにこのアドレスに追加されます。チェックサムはリカバリフレーズ（ニーモニック）にも存在する。

> somme de contrôle "の英訳は "checksum "である。フランス語では "checksum "を直接使うのが一般的です。
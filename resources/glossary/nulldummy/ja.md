---
term: NULLDUMMY
---
OP_CHECKMULTISIG`および`OP_CHECKMULTISIGVERIFY`オペコードで使用されるダミー要素は空のバイト配列（`OP_0`）であることを要求するSegWitソフトフォークのBIP147で導入されたコンセンサスルール。この対策は、この要素に `OP_0` 以外の値を指定することを禁止することで、マレービリティ・ベクトルを排除するために実装された。
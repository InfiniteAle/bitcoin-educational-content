---
term: mtp（過去の中央値）
---
この概念は、ビットコインのプロトコルにおいて、ネットワークのコンセンサスのタイムスタンプのマージンを決定するために使用される。MTP は直近 11 ブロックのマイニングのタイムスタンプの中央値として定義される。この指標を使用することで、不一致が発生した場合に正確な時間についてノード間の不一致を避けることができます。MTPは当初、ブロックのタイムスタンプの有効性を過去と照合して検証する ために使用されていた。BIP113 以降は、タイムロックトランザクション（`nLockTime`、 `OP_CHECKLOCKTIMEVERIFY`、`nSequence`、`OP_CHECKSEQUENCEVERIFY`）の有効性を検証するためのネットワーク時間の基準としても使用されている。
---
term: SIGHASH_ALL/SIGHASH_ACP

---
Тип флага SigHash (`0x81`) в сочетании с модификатором `SIGHASH_ANYONECANPAY` (`SIGHASH_ACP`), используемым в подписях транзакций Bitcoin. Эта комбинация указывает, что подпись применяется ко всем выходам и только к определенному входу транзакции. `SIGHASH_ALL | SIGHASH_ANYONECANPAY` позволяет другим участникам добавлять дополнительные входы в транзакцию после ее первоначальной подписи. Это особенно полезно в сценариях совместной работы, таких как краудфандинговые транзакции, где различные участники могут добавлять свои собственные входы, сохраняя целостность выходов, зафиксированных первоначальным подписантом.
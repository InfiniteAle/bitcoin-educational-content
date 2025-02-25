---
term: SIGHASH FLAG

---
比特币交易中的一个参数，用于确定交易的哪些部分（输入和输出）被相关签名覆盖，从而变得不可更改。SigHash 标志是添加到每个输入数字签名中的一个字节。因此，SigHash 标志的选择直接影响到交易的哪些部分被签名冻结，哪些部分之后仍可修改。这种机制可确保签名按照签名者的意图准确、安全地提交交易数据。主要有三种 SigHash 标志：


- SIGHASH_ALL` (`0x01`)：签名适用于事务的所有输入和输出，从而完全锁定它们；
- SIGHASH_NONE`（`0x02`）：签名适用于所有输入，但不适用于所有输出，允许在签名后修改输出；
- SIGHASH_SINGLE` (`0x03`)：签名涵盖所有输入，只有一个输出与签名输入的索引相对应。

除了这三种 SigHash 标志外，修改器 `SIGHASH_ANYONECANPAY` (`0x80`)还可以与前面的每种类型结合使用。使用该修改器时，只有部分输入是有符号的，其他输入可以修改。以下是使用修改器的现有组合：


- `SIGHASH_ALL | SIGHASH_ANYONECANPAY` (`0x81`)：签名适用于单个输入，同时涵盖事务的所有输出；
- SIGHASH_NONE | SIGHASH_ANYONECANPAY` (`0x82`)：签名只涉及单个输入，不承诺任何输出；
- SIGHASH_SINGLE | SIGHASH_ANYONECANPAY` (`0x83`)：签名适用于单个输入，且仅适用于与该输入具有相同索引的输出。

> ► *"SigHash "有时使用的同义词是 "签名哈希类型"。
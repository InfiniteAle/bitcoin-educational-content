---
term: 无声支付
---
使用静态比特币地址接收付款的方法，无需重复使用地址，无需交互，不同付款和静态地址之间也没有可见的链上链接。这种技术无需为每笔交易生成新的、未使用的收款地址，从而避免了比特币中收款人必须向付款人提供新地址的常见互动。

使用静默支付时，付款人使用收款人的公钥（支出公钥和扫描公钥）和自己的私钥总和作为输入，为每笔付款生成一个新地址。只有收款人能用自己的私钥计算出与该付款地址相对应的私钥。加密密钥交换算法 ECDH（*Elliptic-Curve Diffie-Hellman*）用于建立一个共享秘密，然后用来推导接收地址和私人密钥（仅在收款人一方）。收款人必须扫描区块链，检查符合协议标准的每笔交易，才能识别出针对他们的无声支付。与使用通知交易建立支付渠道的 BIP47 不同，无声支付省去了这一步骤，节省了一笔交易。然而，折衷的办法是，收款人必须扫描所有潜在交易，通过应用 ECDH 来确定这些交易是否是针对他们的。

例如，鲍勃的静态地址 $B$ 代表他的扫描公开密钥和支出公开密钥的连接：

$$ B = B_{text{scan}}\文本{ ‖ }B_{text{spend}}$$

这些键可以简单地从以下路径导出：

```text
scan : m / 352' / 0' / 0' / 1' / 0
spend : m / 352' / 0' / 0' / 0' / 0
```

该静态地址由 Bob 发布。爱丽丝使用它向鲍勃进行无声支付。她用这种方法计算出鲍勃的付款地址 $P_0$：

$$ P_0 = B_{text{spend}}+ text{hash}(text{inputHash} \cdot a \cdot B_{text{scan}} \text{ ‖ } 0) \cdot G $$

在哪里？

$$ \text{inputHash} = \text{hash}(\text{outpoint}_L \text{‖ } A) $$

有了


- $B_{text{scan}}$：Bob 的扫描公开密钥（静态地址）；
- $B_{text{spend}}$：鲍勃花费的公开密钥（静态地址）；
- $A$:输入（调整）中的公钥之和；
- $a$:调整后的私钥，即在爱丽丝交易中作为输入消耗的UTXO的`scriptPubKey`中使用的所有密钥对的总和；
- $text{outpoint}_L$：用作 Alice 交易输入的最小 UTXO（按词典顺序）；
- $\text{ ‖ }$：连接（将操作数端对端连接起来的操作）；
- $G$:椭圆曲线 `secp256k1` 的生成点；
- $\text{hash}$：标记为 "BIP0352/SharedSecret "的 SHA256 哈希函数；
- $P_0$:第一个公钥/唯一地址，用于向 Bob 付款；
- $0$:用于生成多个唯一付款地址的整数。

鲍勃通过这种方式扫描区块链，找到他的 "无声支付"：

$$ P_0 = B_{text{spend}}+ \text{hash}(\text{inputHash} \cdot b_{text{scan}} \cdot A \text{ ‖ } 0) \cdot G $$

有了


- $b_{text{scan}}$：鲍勃的私人扫描密钥。

如果他发现 $P_0$ 是一个包含寄给他的无声付款的地址，他就会计算出 $p_0$，即允许他使用 Alice 发送给 $P_0$ 的资金的私人密钥：

$$ p_0 = （ b_{text{spend}}+ text{hash}(\text{inputHash} \cdot b_{text{scan}} \cdot A \text{ ‖ } 0)) \mod n $$

有了


- $b_{text{spend}}$：鲍勃的私人消费密钥；
- $n$：椭圆曲线 `secp256k1` 的阶数。

除了这个基本版本外，标签还可用于从同一个基本静态地址生成多个不同的静态地址，目的是在不不合理地成倍增加扫描工作的情况下，将多种用途分开。
---
term: BIP322

---
提出一个新标准来取代 BIP137，用于用比特币私钥及其相关地址签署信息，以证明地址的所有权。这些签名适用于各种应用，如资金证明、审计和其他需要通过私钥验证地址的应用。与 BIP137 相比，BIP322 采用基于脚本的方法，将消息签名标准扩展到传统地址之外。它允许钱包软件为任何脚本签署信息，这些脚本可以解锁，以花费比特币。要做到这一点，该方法需要通过为虚拟比特币交易生成签名来签署文本。对于传统的 P2PKH 地址，BIP322 仍然与传统的签名格式兼容。
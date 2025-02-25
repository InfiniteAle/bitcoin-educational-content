---
term: 术语： BARE-MULTISIG

---
标准脚本模型 P2MS，用于在 UTXO 上建立支出条件。它允许用多个公钥锁定比特币。要使用这些比特币，必须提供带有预定数量相关私钥的签名。例如，"2/3 "P2MS 有 "3 "个公钥和 "3 "个相关的秘密私钥。要使用这个 P2MS 脚本锁定的比特币，必须使用`3`个私钥中至少`2`个私钥进行签名。这是一个门槛安全系统。这个脚本是加文-安德森（Gavin Andresen）在 2011 年发明的，当时他刚刚接手比特币主客户端的维护工作。如今，P2MS 只在一些应用中得到少量使用。绝大多数现代多重签名使用其他脚本模型，如 P2SH 或 P2WSH。与之相比，P2MS 极为琐碎。它所包含的公钥在收到交易时就会显示出来。使用 P2MS 的成本也比其他多重签名脚本高。
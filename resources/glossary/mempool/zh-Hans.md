---
term: 存储器

---
内存 "和 "池 "的缩写。它指的是一个虚拟空间，在这个空间里，等待纳入区块的比特币交易被集中在一起。当一笔交易在比特币网络上创建和广播时，首先要经过网络节点的验证。如果该交易被认为是有效的，它就会被放置在每个节点的内存池中，直到它被矿工选中纳入一个区块。

值得注意的是，比特币网络中的每个节点都维护自己的 Mempool，因此，不同节点之间的 Mempool 内容在任何时候都可能存在差异。值得注意的是，每个节点的 "bitcoin.conf "文件中的 "maxmempool "参数允许操作员控制其节点用于在 Mempool 中存储待处理交易的 RAM（随机存取内存）的大小。通过限制 Mempool 的大小，节点操作员可以防止 Mempool 占用太多系统资源。该参数的单位是兆字节（MB）。迄今为止，Bitcoin Core 的默认值是 300 MB。

Mempool 中的交易是临时的。在纳入区块并经过一定数量的确认之前，它们不应被视为不可变的。这些交易通常可以被替换或清除。
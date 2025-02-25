---
term: 自私开采

---
挖矿策略（或攻击），即一个矿工或一组矿工故意保留具有有效工作证明的区块，而不立即向网络发布。这样做的目的是在工作量证明方面保持对其他矿工的领先优势，从而有可能让他们连续挖出几个区块并一次性全部发布，从而实现收益最大化。

换句话说，攻击矿工群不是在整个网络验证的最后一个区块上挖矿，而是在他们自己创建的区块上挖矿，这个区块与网络验证的区块不同。这个过程会产生一种区块链的秘密分叉，整个网络都不知道这个分叉，直到这个替代链有可能超过诚实的区块链。一旦攻击矿工的秘密链变得比诚实的公开链更长（即包含更多的累积工作），它就会被广播到整个网络。此时，跟随最长链（累积工作量最多）的网络节点将与这条新链同步。这就是重组的结果。

自私挖矿之所以存在问题，是因为它会浪费网络的部分计算能力，从而降低系统的安全性。如果挖矿成功，还会导致区块链重组，从而影响用户交易确认的可靠性。对于攻击矿工群体来说，这种做法仍然存在风险，因为在公开的最后一个区块上正常挖矿往往比将计算能力分配给可能永远不会超过诚实区块链的秘密分叉更有利可图。重组的区块数量越多，攻击成功的概率就越低。

> ► *"minageégoïste "的英文翻译是 "自私挖矿"。请注意，"自私挖矿 "攻击不应与 "区块扣留 "攻击相混淆。
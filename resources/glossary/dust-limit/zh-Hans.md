---
term: 粉尘限值

---
指网络节点将UTXO视为 "灰尘 "的阈值（以卫星为单位）。这个阈值是标准化规则的一部分，每个节点都可以独立修改。在比特币核心中，这一限制由特定的费率决定，默认设置为每虚拟千字节（sats/kvB）3000 sats。这一限制旨在限制含有极少量比特币的交易的传播。事实上，UTXO 被定义为尘埃意味着它的使用在经济上是不合理的：花掉这个 UTXO 的成本比简单地放弃它更高。如果花掉灰尘是不合理的，那么这就意味着这种花费只能由外部动机（通常是恶意的）驱动。如果恶意行为者试图让网络中含有微不足道金额的交易达到饱和，从而增加节点的运行负荷，并可能阻止节点处理其他合法交易，那么这就会成为一个问题。打个比方（尽管我承认这个比方略显笨拙），这就有点像有人试图用 1 美分硬币支付 100 欧元的购物篮，以便在结账时阻止其他顾客。
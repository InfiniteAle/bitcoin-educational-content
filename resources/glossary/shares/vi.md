---
term: SHARES

---
In the context of mining pools, a share is an indicator used to quantify an individual miner's contribution within the pool. This measure serves as the basis for calculating the reward that the pool redistributes to each miner. Each share corresponds to a hash that satisfies a difficulty target lower than that of the Bitcoin network.

To explain with an analogy, consider a 20-sided die. On Bitcoin, suppose that the proof of work requires rolling a number lower than 3 to validate a block (that is, achieving a result of 1 or 2). Now, imagine that within a mining pool, the difficulty target for a share is set at 10. Thus, for an individual miner in the pool, each dice roll that results in a number lower than 10 counts as a valid share. These shares are then transmitted to the pool by the miner, in order to claim their reward, even if they do not correspond to a valid result for a block on Bitcoin.

For each hash calculated, an individual miner in a pool can encounter three different scenarios:


- If the hash value is greater than or equal to the pool's set difficulty target for a share, then this hash is of no use. The miner then changes their nonce to attempt a new hash: `hash > share > block`.
- If the hash is lower than the difficulty target of the share, but greater than or equal to the difficulty target of Bitcoin, then this hash constitutes a valid share that is, however, not sufficient to validate a block. The miner can send this hash to their pool to claim the reward associated with the share: `share > hash > block`.
- If the hash is lower than the difficulty target of the Bitcoin network, it is considered both a valid share and a valid block. The miner transmits this hash to their pool, which hurries to broadcast it on the Bitcoin network. This hash is also counted as a valid share for the miner: `share > bloc > hash`.

![](../../dictionnaire/assets/32.webp)

This share system is used to estimate the work done by each individual miner within a pool, without having to individually recalculate all the hashes generated by a miner, which would be completely inefficient for the pool.

Mining pools adjust the difficulty of shares to balance the verification load and ensure that every miner, whether small or large, submits shares approximately every few seconds. This allows for an accurate calculation of each miner's hashrate and the distribution of rewards according to the chosen method of compensation calculation (PPS, PPLNS, TIDES...).

> ► *In French, "shares" can be translated as "part".*
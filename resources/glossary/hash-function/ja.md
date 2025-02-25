---
term: ハッシュ関数
---
可変サイズの入力（メッセージと呼ばれる）を受け取り、固定サイズの出力（ハッシュ、ハッシュ、ダイジェスト、フィンガープリントと呼ばれる）を生成する数学関数。ハッシュ関数は暗号化において広く使われているプリミティブである。ハッシュ関数は、安全な文脈での使用に適した特殊な性質を持つ：


- 前像耐性：特定のハッシュを生成するメッセージを見つけるのは非常に困難でなければならない。すなわち、ハッシュ$h$に対して、$h=H(m)$となるような前像$m$を見つけるのは非常に困難でなければならない；
- 第二の前像抵抗：あるメッセージ$m_1$が与えられたとき、$H(m_1)=H(m_2)$となるような（$m_1$とは異なる）別のメッセージ$m_2$を見つけるのは非常に困難でなければならない；
- 耐衝突性：H(m_1)=H(m_2)$となるような2つの異なるメッセージ$m_1$と$m_2$を見つけるのは非常に難しい；
- 耐タンパー性：入力の小さな変化が、出力に大きく予測不可能な変化をもたらすこと。

ビットコインの文脈では、ハッシュ関数は、プルーフ・オブ・ワークメカニズム（*Proof-of-Work*）、トランザクション識別子、アドレス生成、チェックサム計算、Merkleツリーなどのデータ構造の作成など、いくつかの目的で使用されている。プロトコル側では、ビットコインは `SHA256d` 関数を独占的に使用しており、これは `HASH256` という名前でもあり、二重の `SHA256` ハッシュから構成されている。これは二重の `SHA256` ハッシュから構成される。`HASH256` は特定のチェックサムの計算にも使用され、特に拡張キー（`xpub`, `xprv`...）に使用される。ウォレット側では、以下も使用される：


- 単純な `SHA256` でニーモニックフレーズのチェックサムを行う；
- SHA512`は、決定論的なウォレットと階層的なウォレットを導き出す過程で使用される `HMAC` と `PBKDF2` アルゴリズムに含まれている；
- HASH160` は `SHA256` と `RIPEMD160` を連続して使用することを示す。HASH160` は受信アドレスの生成 (P2PK と P2TR を除く) や、拡張鍵の親鍵のフィンガープリントの計算に使用される。

> 英語では「ハッシュ関数」と呼ばれる。
---
term: ASICBOOST
---
ASICBOOSTは2016年に考案されたアルゴリズム最適化手法で、ヘッダーの各ハッシュ試行に必要な計算量を削減することで、ビットコインのマイニング効率を約20％向上させるように設計されている。この手法は、マイニングに使用されるSHA256ハッシュ関数の特徴を利用したもので、データをブロックに分割してから処理する。ASICBOOSTは、これらのブロックの1つを複数回のハッシュ試行にわたって変更せずに保持するため、採掘者は複数回の試行にわたって、このブロックに対する作業の一部のみを行うことができます。このデータ共有により、以前の計算結果の再利用が可能になるため、有効なハッシュを見つけるために必要な総計算回数が削減されます。

ASICBOOSTは2つの形態で使用できる：OvertASICBOOSTとCovert ASICBOOSTである。Overt ASICBOOSTは、ブロックの`nVersion`フィールドをnonceとして使用し、実際の`Nonce`を変更しないため、誰でも見ることができる。Covert形式は、Merkleツリーを使用することで、これらの変更を隠蔽しようとするものである。しかし、この2つ目の方法は、2つ目のメルクルツリーを使用するために必要な計算回数が増えるため、SegWitの導入以降、あまり有効ではなくなりました。

要約すると、ASICBOOSTにより、マイナーはすべてのハッシュ試行で真の完全なSHA256を実行する必要がなくなり、結果の一部が変更されないため、マイナーの作業がスピードアップする。
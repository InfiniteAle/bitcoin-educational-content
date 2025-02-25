---
term: ファイバー
---
Fast Internet Bitcoin Relay Engine*」の略称。2016年にMatt Corallo氏によって設計された、ビットコインブロックの世界中への配布を高速化するためのプロトコルである。その目標は、伝搬遅延を物理的限界に限りなく近づけることだった。FIBREは、参加者が採掘したブロックの割合が、ネットワーク内での位置に関係なく、コンピューティングパワーの面でその貢献度を正確に反映するようにすることで、採掘機会をより公平に分配することを目指した。

実際、ブロック伝送の待ち時間は、大規模で接続の良いマイニンググループに有利に働く可能性があり、多くの場合、互いに近くに位置しているため、小規模なグループは不利になります。この現象は、時間の経過とともにマイニングの集中化を促進し、システム全体のセキュリティを低下させる可能性がある。この問題に対処するため、FIBREはエラー訂正コードを導入し、パケットロスを相殺するための追加データの送信や、BIP152で説明されているようなコンパクトなブロックの使用を導入した。それにもかかわらず、FIBREは2020年に放棄された。その主な理由は、1人のメンテナに依存していたことと、BIP152の採用によってそのようなシステムの必要性が低くなったことである。
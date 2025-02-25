---
term: アンカー出力
---
Lightningチャネル内の取引手数料の管理を改善することを目的とした提案。Lightningチャネルの状態が変わるたびに、関係者はチャネル内の新しい資金配分を反映した新しいコミットメントトランザクションを作成し、署名する。このメカニズムの問題は、トランザクションの作成時に取引手数料を決定することにある。実際、ビットコインネットワーク上の取引手数料は、上方にも下方にも大きく変動する。最後のコミットメント取引に設定された手数料がチャネルの一方的な閉鎖時に不十分であった場合、取引の確認に相当な時間がかかるだけでなく、時間的ロック機構（タイムロック）によって資金が盗まれる可能性もある。アンカー・アウトプットは、将来の手数料をカバーするために、コミットメント・トランザクションの資金のごく一部を留保する。ネットワークが混雑し手数料が上昇した場合、アンカー出力はコミットメントトランザクションの作成後にトランザクション手数料を修正することを可能にし、ライトニングチャネルの十分な速やかな閉鎖を保証する。
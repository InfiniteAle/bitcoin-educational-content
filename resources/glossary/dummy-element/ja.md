---
term: ダミー・エレメント
---
OP_CHECKMULTISIG` と `OP_CHECKMULTISIGVERIFY` というオペコードがトランザクションの署名を検証する際に消費する、追加の不要な要素を指す。歴史的な1つずれのバグ（ユニットシフトエラー）により、これら2つのオペコードは基本的な機能に加えて、スタックから余分な要素を取り除きます。そのため、エラーを回避するために、`scriptSig` の先頭にダミーの値を含めることが必須となる。この不要な値が「*ダミー要素*」と呼ばれるものである。P2MS規格を導入したBIP11では、ダミー値として`OP_0`を使用することを推奨していた。しかし、この標準はコンセンサスルールレベルでは適用されず、トランザクションを無効にすることなく、どのような値でもダミー要素に入れることができた。このように、ダミー要素はトランザクションの不正性を引き起こすベクトルであった。SegWitのソフトフォークで導入されたBIP147は、このダミー要素を厳密に空のバイト配列（`OP_0`）とすることを義務付け、コンセンサスルールに準拠しないトランザクションを無効にすることで、この要素に関連する不正性を排除した。NULLDUMMY`と名付けられたこのルールは、SegWitとSegWit以前のトランザクションの両方に適用される。
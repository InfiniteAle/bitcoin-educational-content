---
term: 分析的ヒューリスティック
---
ビットコインチェーンの分析ヒューリスティックとは、取引で観察された特徴に基づいてブロックチェーン上のビットコインの流れを追跡するために使用される経験的手法の一群である。ヒューリスティックとは、問題解決への実践的なアプローチであり、多くの場合近似的な手法を用いますが、与えられた目標を達成するための十分に優れた解決策を表します。これらのヒューリスティックはかなり信頼できる結果をもたらすが、絶対的な精度を持つことはない。言い換えれば、連鎖分析では常に、導き出される結論にある程度の尤度が含まれる。例えば、2つのアドレスが同じエンティティに属することは、多かれ少なかれ確実に推定できるかもしれないが、完全な確実性は常に手の届かないところにある。連鎖分析の目的は、まさにエラーのリスクを最小化するために様々なヒューリスティックを集約することにある。いわば、より現実に近づくための証拠の集積なのである。この文脈では、内部ヒューリスティックと外部ヒューリスティックが区別される。

内部ヒューリスティックは、個々のトランザクションに特有の特徴に注目する。それらの分析には、UTXOの量、使用されたスクリプト、バージョン、またはロックタイ ムなどの要素が含まれる。例えば、ラウンドペイメントヒューリスティックは、トランザクショ ンアウトプットの金額がラウンド数である場合、そのトランザクションがペイメントである可能性が高いと識別するこ とを可能にする。これらのヒューリスティックは、しばしば小銭（同じユーザーに戻された金 銭）を識別することを可能にし、その結果トレースを継続することができる。

一方、外部ヒューリスティックは、取引そのものを超えた類似点や特徴を分析する。これらはトランザクション環境全体を包含する。例えば、複数のトランザクションにまたがるアドレスの再利用は外部ヒューリスティックである。CIOHもその一つである。
---
term: OP_2DUP (0X6E)

---
Дублирует два верхних элемента стека, а затем помещает их на вершину стека. Например, если стек имеет вид:

```text
A
B
C
D
```

`OP_2DUP` будет производить:

```text
A
B
A
B
C
D
```
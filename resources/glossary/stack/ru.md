---
term: STACK

---
В контексте языка сценариев, используемого для применения условий расходования средств на Bitcoin UTXO, стек - это структура данных "LIFO" (*Last In, First Out*), которая служит для хранения временных элементов во время выполнения сценария. Каждая операция в скрипте манипулирует этими стеками, где элементы могут быть добавлены (*push*) или удалены (*pop*). Сценарии используют стеки для оценки выражений, хранения временных переменных и управления условиями.

Во время выполнения биткоин-скрипта могут использоваться два стека: основной и alt (альтернативный). Основной стек используется для большинства операций скрипта. Именно в этом стеке скрипты добавляют, удаляют или манипулируют данными. Альтернативный стек, с другой стороны, служит для временного хранения данных во время выполнения скрипта. Специальные опкоды, такие как `OP_TOALTSTACK` и `OP_FROMALTSTACK`, позволяют переносить элементы из основного стека в альтернативный и наоборот.

Например, во время проверки транзакции подписи и открытые ключи помещаются в основной стек и обрабатываются последовательными операционными кодами для проверки соответствия подписей ключам и данным транзакции.

> ► *В английском языке "pile" переводится как "стопка". Английский термин обычно используется даже во французском языке во время технических дискуссий.*
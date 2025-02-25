---
term: РЕГУЛИРОВКА ТРУДНОСТЕЙ

---
Корректировка сложности - это периодический процесс, который переопределяет целевую сложность для механизма доказательства работы (майнинга) в биткойне. Это событие происходит каждые 2016 блоков (примерно раз в две недели). Оно служит для увеличения или уменьшения коэффициента сложности (также называемого целью сложности) в зависимости от того, как быстро были найдены последние 2016 блоков. Корректировка направлена на поддержание стабильной и предсказуемой скорости добычи блоков с частотой один блок каждые 10 минут, несмотря на колебания вычислительных мощностей, задействованных майнерами. Изменение сложности в ходе корректировки ограничено коэффициентом 4. Формула, которую выполняют узлы для расчета новой цели, выглядит следующим образом:

$$N = A \cdot \left(\frac{T}{1,209,600}\right)$$

&nbsp;

Где:


- $N$: Новая цель;
- $A$: Старая цель последних 2016 блоков;
- $T$: Общее фактическое время последних 2016 блоков в секундах;
- $1,209,600$: Целевое время в секундах для создания 2016 блоков с 10-минутным интервалом между каждым.

> ► *Во французском языке термин "reciblage" иногда также используется для обозначения корректировки. В английском языке этот термин называется "Difficulty Adjustment".*
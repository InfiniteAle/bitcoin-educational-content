---
term: РАСШИРЕННЫЙ КЛЮЧ

---
Последовательность символов, объединяющая ключ (открытый или закрытый), связанный с ним код цепочки и ряд метаданных. Расширенный ключ объединяет все элементы, необходимые для получения дочерних ключей, в один идентификатор. Они используются в детерминированных и иерархических кошельках и могут быть двух типов: расширенный открытый ключ (используется для получения дочерних открытых ключей) или расширенный закрытый ключ (используется для получения как дочерних закрытых, так и открытых ключей). Таким образом, расширенный ключ включает в себя несколько различных частей данных, описанных в BIP32, в следующем порядке:


- Префикс: `prv` и `pub` - это HRP (Human Readable Part), указывающий на то, является ли это расширенный закрытый ключ (`prv`) или расширенный открытый ключ (`pub`). Первая буква префикса обозначает версию расширенного ключа: `x` для Legacy или SegWit V1 на Bitcoin, `t` для Legacy или SegWit V1 на Bitcoin Testnet, `y` для Nested SegWit на Bitcoin, `u` для Nested SegWit на Bitcoin Testnet, `z` для SegWit V0 на Bitcoin, `v` для SegWit V0 на Bitcoin Testnet.
- Глубина, которая указывает количество производных от главного ключа для достижения расширенного ключа;
- Отпечаток родительского ключа. Представляет собой первые 4 байта `HASH160` родительского открытого ключа;
- Индекс. Это номер пары среди ее братьев и сестер, из которой получен расширенный ключ;
- Код цепи;
- Байт подстановки, если это закрытый ключ `0x00`;
- Закрытый или открытый ключ;
- Контрольная сумма. Представляет собой первые 4 байта `HASH256` остальной части расширенного ключа.

На практике расширенный открытый ключ используется для генерации адресов получения и наблюдения за транзакциями по счету без раскрытия связанных с ним закрытых ключей. Это позволяет, например, создать так называемый кошелек "только для наблюдения". Однако важно отметить, что расширенный открытый ключ является чувствительной информацией для конфиденциальности пользователя, поскольку его раскрытие может позволить третьим лицам отслеживать транзакции и видеть баланс связанного счета.
---
term: ИНДЕКС БЛОКОВ

---
Структура данных LevelDB в Bitcoin Core, в которой хранятся метаданные обо всех блоках. Каждая запись в этом индексе содержит такие сведения, как идентификатор блока, его высота в блокчейне, указатель на блок в базе данных и другие метаданные. Такая индексация позволяет быстро найти блок в памяти.
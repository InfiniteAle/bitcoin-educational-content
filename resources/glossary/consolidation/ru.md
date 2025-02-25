---
term: КОНСОЛИДАЦИЯ

---
Специфическая операция, в которой несколько мелких UTXO объединяются в один вход, чтобы на выходе получить один, более крупный UTXO. Эта операция является транзакцией, совершаемой в собственном кошельке. Цель консолидации - воспользоваться периодами, когда комиссии в сети Биткойн низкие, чтобы объединить несколько мелких UTXO в один более крупный по стоимости. Таким образом, она предвосхищает обязательные расходы в случае повышения комиссии, позволяя сэкономить на будущих комиссиях за транзакции.

Действительно, транзакции с большим количеством вводимых данных являются более тяжелыми и, следовательно, более дорогими. Помимо экономии на комиссии за транзакции, консолидация - это еще и форма долгосрочного планирования. Если в вашем кошельке хранятся очень маленькие UTXO, они могут стать непригодными для использования, если сеть Биткойна вступит в длительный период высоких комиссий. Например, если вам нужно потратить UTXO в размере 10 000 сатов, а минимальная плата за майнинг составляет 15 000 сатов, расходы превысят стоимость самого UTXO. Тогда использование таких небольших UTXO становится экономически нерациональным и остается непригодным до тех пор, пока не снизятся сборы. Такие UTXO принято называть "пылью" Регулярно консолидируя свои мелкие UTXO, вы снижаете риск, связанный с увеличением комиссии.

Однако важно отметить, что сделки консолидации можно распознать при анализе цепочки. Такая транзакция указывает на эвристику общего владения входом (CIOH), означающую, что входы консолидационной транзакции принадлежат одному субъекту. Это может иметь последствия с точки зрения конфиденциальности для пользователя.

![](../../dictionnaire/assets/7.webp)
# Разработка модели предсказывающей исход(победа/поражение/ничья) в футбольном контексте


**1.0 Проблемы при первичном запуске:**
- недостаточный объем данных в датасете(как данные так и малое количество параметров)
- дисбаланс классов, что привело к главной проблеме - модель постоянно выбирает только домашнюю команду
- неудовлетворительная точность модели

**1.1 Что сделано по проблемам:**

Увеличение количества эпох и глубины, а также уменьшение шага привело к понижению точности модели. В связи с этим было принято решение на данном этапе использовать RandomOverSampler.
- добавлен RandomOverSampler, 3 исхода, баланс каждого как 100:кол-во исходов ~3.33 каждый
- оптимальный вариант итераций 50
- использование весов как [1,1,1]
- глубина 4
- добавлены логи

**1.2 Что получено на выходе:**

Модель не предъвзято относится к домашней команде, повышена общая точность модели, вывод процентной вероятности к каждому исходу

**2.0 Что осталось**

Несмотря на повышенную точность и не предъвзятость к домашнему классу при тестировании модель редко, но совершает ошибки на исторических данных
- Расширить датасет и признаки ~ 5000 строк
- Избавиться от кодировки cp

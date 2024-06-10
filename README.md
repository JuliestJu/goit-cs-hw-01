# Технічний опис завдань

## Домашнє завдання складається з двох незалежних завдань.

## Завдання 1

**Розробіть програму на асемблері, яка виконує обчислення арифметичного виразу `b - c + a`.**

Використовуйте як основу приклад програми для обчислення `a + b - c`, представлений у конспекті (посилання на папку репозиторію до конспекту), але з необхідними модифікаціями для вирішення цього завдання.

### Покрокова інструкція

1. Вивчіть код програми, що обчислює `a + b - c`, наведений у конспекті.
2. Модифікуйте програму так, щоб вона виконувала обчислення за формулою `b - c + a`.
3. Після внесення змін у код скомпілюйте та запустіть програму, щоб перевірити, чи коректно вона обчислює вираз `b - c + a`.
4. Ваша програма повинна виводити результат обчислення на екран.
5. Після запуску програми у DOSBox зробіть скріншот вікна DOSBox із відображеним результатом виконання вашої програми.

### Критерії прийняття

- Програма коректно обчислює вираз `b - c + a` та виводить результат обчислення на екран.
- Зроблено та прикріплено скріншот вікна DOSBox із відображеним результатом виконання програми.

## Завдання 2

**Розширте інтерпретатор для підтримки операцій множення та ділення, а також обробки виразів з дужками.**

У вас є початковий код інтерпретатора з конспекту, який вміє обробляти арифметичні вирази, включаючи операції додавання та віднімання (посилання на папку репозиторію до конспекту). Ваше завдання полягає в розширенні цього інтерпретатора таким чином, щоб він також підтримував операції множення та ділення, а також коректно обробляв вирази, що містять дужки.

### Покрокова інструкція

1. **Розширте лексер Lexer**
   - Додайте нові типи токенів для операцій множення (`MUL`), ділення (`DIV`) та дужок, які відкривають (`LPAREN`) та закривають (`RPAREN`) частину арифметичного виразу.
   - Модифікуйте метод `get_next_token` класу Lexer так, щоб він розпізнавав ці нові символи.

2. **Модифікуйте парсер Parser**
   - Додайте метод `factor` для обробки чисел та виразів у дужках.
   - Змініть метод `term`, щоб він включав обробку множення та ділення.
   - Внесіть відповідні зміни в метод `expr` для підтримки нової ієрархії операцій.

3. **Оновіть Інтерпретатор Interpreter**
   - Доповніть метод `visit_BinOp` у класі Interpreter так, щоб він міг обробляти операції множення та ділення.

4. **Тестування**
   - Перевірте коректність роботи інтерпретатора на різних арифметичних виразах, включаючи вирази з дужками, наприклад `(2 + 3) * 4` повинно дати результат `20`.

### Тестові вирази для перевірки

1. `3 + 5` -> `8`
2. `10 - 2` -> `8`
3. `4 * 2` -> `8`
4. `8 / 4` -> `2.0`
5. `(3 + 5) * 2` -> `16`
6. `((3 + 5) * 2) / 4` -> `4.0`
7. `3 + 5 * (2 - 1) / 4` -> `4.25`
8. `(10 - (2 + 3)) * (4 / 2)` -> `10.0`

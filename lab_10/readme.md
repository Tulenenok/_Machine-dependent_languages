## Задание:

Реализовать скалярное произведение векторов, или множества пар векторов, или другую операцию над векторами, или умножение матриц, или другую операцию над матрицами в виде ассемблерной вставки с использованием расширений процессора x86-64.<br>

Сравнить производительность решения с кодом, написанным на C/C++.

### Я реализовал скалярное произведение векторов командами SSE.
Поначалу я хотел сделать что-то сложное с матрицами. Нагуглив код переменожения матриц командами SSE, я понял, что он мало чем отличается от обычного. Векторное произведение векторов тоже сильно не преображается от использования команд SSE. А вот скалярное произведение делается очень красиво за счёт команды `mulps`, которая переменожает соответствующие части своих операндов, что и нужно в скалярном произведении.

### Компиляция: 
`gcc main.c -std=c99 -Werror -Wall -Wpedantic -Wextra -masm=intel -o main.exe`

### Да, я знаю про существование более быстрого, эффективного и современного AVX...
Но я не смог разобраться с ним с ходу, а тратить много времени я сейчас не могу, а хочется...

### Полезные ссылки:
- [Неплохие описания команд на русском](https://www.club155.ru/x86cmdsimd)
- [Подробные описания команд с расшифровкой](https://www.felixcloutier.com/x86/)
- [Чуть менее подробные, но более наглядные описания команд](https://c9x.me/x86/)

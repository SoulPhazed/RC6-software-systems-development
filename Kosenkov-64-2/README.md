Лабораторная работа №2 по курсу "Разработка программных систем"
Тема: "Многопоточное программирование"
Вариант 25

Выполнил: Косенков Александр Александрович
Студент группы РК6-64

------------------------------------------

Программа, обеспечивающая обработку строк со стандартного потока ввода, использующая 3 потока, где нулевой поток
обеспечивает чтение строк, а два оставшихся обеспечивают обработку в соответствии с режимом работы.

Режимы работы:
- Поток 1:
    - 1 - трансляция строки в неизменном виде
    - 2 - инвертирование строки - первый символ становится последним и т.д
    - 3 - обмен соседних символов - нечетный становится на место четного и наоборот
    - 4 - перевод в КОИ-8 - установление в 1 старшего (8-ого) бита каждого символа
- Поток 2:
    - 1 - трансляция строки в неизменном виде
    - 2 - перевод всех символов строки в "верхний регистр"
    - 3 - перевод всех символов строки в "нижний регистр"
    - 4 - смена "регистра" всех символов строки

Изменение режима работы потоков осуществляется комбинацией `Ctrl+C`.
В свою очередь установка режима осуществляется указанием двух подряд идущих цифр, обозначающих режимы работы первого и
второго потоков соответственно.
Например: `24` - установит первый поток в режим 2, а второй в режим 4.
Также, при указании цифры `0` в качестве режима у соответствующего потока - режим останется неизменным.

Выход из программы осуществляется комбинацией `Ctrl+D`, обозначающей конец ввода.

Компиляция и сборка: `make clean && make`
Запуск программы: `./lab2`
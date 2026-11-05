#include <stdio.h>
#include <math.h>
#include <locale.h>

double f1(double x)
{
    if (x <= 3)
        return x * x - 3 * x + 9;
    else
        return 1.0 / (x * x * x + 3);
}

double f2(double x)
{
    return x * exp(sin(x * x));
}

int main()
{
    setlocale(LC_ALL, "Russian");

    double x;
    int choice;

    printf("Введите значение x: ");
    scanf("%lf", &x);

    printf("\nМЕНЮ:\n");
    printf("1. Вычислить F1(x)\n");
    printf("2. Вычислить F2(x)\n");
    printf("3. Произведение функций\n");
    printf("4. Разность квадратов функций\n");
    printf("5. Удвоенная сумма функций\n");

    printf("\nВыберите операцию: ");
    scanf("%d", &choice);

    switch (choice)
    {
        case 1:
            printf("F1(x) = %.6lf\n", f1(x));
            break;

        case 2:
            printf("F2(x) = %.6lf\n", f2(x));
            break;

        case 3:
            printf("Произведение = %.6lf\n",
                f1(x) * f2(x));
            break;

        case 4:
            printf("Разность квадратов = %.6lf\n",
                f1(x) * f1(x) - f2(x) * f2(x));
            break;

        case 5:
            printf("Удвоенная сумма = %.6lf\n",
                2 * (f1(x) + f2(x)));
            break;

        default:
            printf("Неверный пункт меню!\n");
            break;
    }

    return 0;
}
# Лабораторная работа 1 (Домашнее задание)

## Условие задачи
Написать программу, которая выводит в консоль заданную геометрическую фигуру (спортивный инвентарь — гантель) с использованием функции `puts()`. Оформить вывод в виде рамки, используя символы `*`.

## 1. Алгоритм и блок-схема

### Алгоритм
1. **Начало**
2. Установить русскую локаль для корректного вывода текста (`setlocale`).
3. С помощью функции `puts()` вывести символы, образующие гантель.
4. **Конец**

### Блок-схема

<img width="222" height="362" alt="Диаграмма без названия drawio (3)" src="https://github.com/user-attachments/assets/61c963a9-1552-4bbb-8195-9bf5935609a2" />


## 2. Реализация программы

Исходный код программы: [namee.c](namee.c)

## 3. Результаты работы программы

**Пример работы программы (вывод гантели):**

dckvkd

## 4. Информация о разработчике

Носырева Элла 
БОТИ-261

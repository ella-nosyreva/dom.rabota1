#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
#include <math.h>

// Прототипы функций
void print_menu();
float area_rhombus(float d1, float d2);
void definition_rhombus();
void draw_rhombus(int size, char symbol);
int is_point_in_rhombus(float x, float y, float d1, float d2);

int main()
{
    setlocale(LC_ALL, "RUS");

    int choice = -1;
    float d1, d2, area;
    int size;
    char symbol;

    do
    {
        print_menu(); // Вызываем функцию для вывода текста меню
        scanf("%d", &choice);

        // Меню через switch
        switch (choice)
        {
            case 1:
                printf("Введите первую диагональ: ");
                scanf("%f", &d1);
                printf("Введите вторую диагональ: ");
                scanf("%f", &d2);
                area = area_rhombus(d1, d2);
                printf("Площадь ромба: %.2f\n", area);
                break;

            case 2:
                definition_rhombus();
                break;

            case 3:
                printf("Введите размер ромба (например, 4): ");
                scanf("%d", &size);
                printf("Введите символ для рисования: ");
                scanf(" %c", &symbol);
                draw_rhombus(size, symbol);
                break;

            case 4:
            {
                float x, y, d1_test, d2_test;
                printf("Введите X: ");
                scanf("%f", &x);
                printf("Введите Y: ");
                scanf("%f", &y);
                printf("Введите диагональ по X: ");
                scanf("%f", &d1_test);
                printf("Введите диагональ по Y: ");
                scanf("%f", &d2_test);

                if (is_point_in_rhombus(x, y, d1_test, d2_test))
                    printf("Точка ПОПАДАЕТ в ромб.\n");
                else
                    printf("Точка НЕ ПОПАДАЕТ в ромб.\n");
                break;
            }

            case 0:
                printf("Выход из программы...\n");
                break;

            default:
                printf("Неверный выбор! Введите число от 0 до 4.\n");
                break;
        }
    } while (choice != 0);

    return 0;
}

// Отдельная функция для вывода меню, чтобы не засорять main
void print_menu()
{
    printf("\n=== МЕНЮ (Фигура: Ромб) ===\n");
    printf("1. Рассчитать площадь\n");
    printf("2. Вывести определение фигуры\n");
    printf("3. Нарисовать фигуру\n");
    printf("4. Проверить, попадает ли точка в ромб\n");
    printf("0. Выход\n");
    printf("Выберите действие: ");
}

// --- Реализация остальных функций ---

float area_rhombus(float d1, float d2)
{
    return (d1 * d2) / 2.0;
}

void definition_rhombus()
{
    printf("\nРомб - это параллелограмм, у которого все стороны равны.\n");
    printf("Площадь ромба равна половине произведения его диагоналей.\n");
}

void draw_rhombus(int size, char symbol)
{
    printf("\n");
    for (int i = 0; i < size; i++)
    {
        for (int j = 0; j < size - 1 - i; j++) printf(" ");
        for (int j = 0; j < 2 * i + 1; j++) printf("%c", symbol);
        printf("\n");
    }
    for (int i = size - 2; i >= 0; i--)
    {
        for (int j = 0; j < size - 1 - i; j++) printf(" ");
        for (int j = 0; j < 2 * i + 1; j++) printf("%c", symbol);
        printf("\n");
    }
    printf("\n");
}

int is_point_in_rhombus(float x, float y, float d1, float d2)
{
    if (d1 <= 0 || d2 <= 0) return 0;
    float check = (fabs(x) / (d1 / 2.0f)) + (fabs(y) / (d2 / 2.0f));
    return (check <= 1.0f);
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

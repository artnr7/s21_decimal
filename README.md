# S21 Decimal -  Высокоточная арифметика

## 🔢 Описание
**Библиотека `s21_decimal`** реализует **высокоточную арифметику** с десятичными числами по спецификации **S21**. Поддерживает все основные операции с точностью до **28 знаков**.

## 🚀 Быстрый старт

```bash
# Клонировать репозиторий
git clone <repo-url>
cd s21_decimal

# Собрать библиотеку
make all

# Запустить тесты
make test

# Сгенерировать отчёт покрытия
make gcov_report
```

## 📋 Makefile цели

| Цель               | Описание                     | Результат                |
| ------------------ | ---------------------------- | ------------------------ |
| `make all`         | **Сборка** библиотеки        | `s21_decimal.a`          |
| `make rebuild`     | **Пересборка** (clean + all) | Чистая библиотека        |
| `make test`        | **Unit-тесты** (Check)       | `test_exec`              |
| `make gcov_report` | **Покрытие кода**            | `report_lcov/index.html` |
| `make clean`       | **Очистка**                  | Удаление артефактов      |

## 🏗️ Структура проекта

```
s21_decimal/
├── source/           # Исходный код
│   ├── arithmetic.c      # Арифметика (+, -, *, /)
│   ├── binary_*.c        # Бинарные операции
│   ├── compare.c         # Сравнения (==, >, <)
│   ├── converter.c       # Конвертеры (int, float)
│   ├── round.c           # Округления
│   ├── ten_*.c          # Десятичные функции
│   └── utils.c           # Утилиты
├── test/             # Unit-тесты
├── Makefile          # Сборка и тесты
└── s21_decimal.a     # Итоговая библиотека
```

## 🔧 Технический стек

```
🛠️  C11 • GCC
✅ Check framework (unit-тесты)
📊 LCOV + GenHTML (покрытие)
```

## 📊 Функционал

| Группа          | Функции                                                                                        | Описание               |
| --------------- | ---------------------------------------------------------------------------------------------- | ---------------------- |
| **Арифметика**  | `add`, `sub`, `mul`, `div`, `mod`                                                              | Базовые операции       |
| **Сравнение**   | `is_eq`, `is_gt`, `is_lt`, `is_not_eq`                                                         | Логические сравнения   |
| **Конвертация** | `from_int_to_decimal`, `from_float_to_decimal`, `from_decimal_to_int`, `from_decimal_to_float` | Приведения типов       |
| **Округление**  | `round`, `floor`, `truncate`, `negate`                                                         | Математические функции |
| **Бины**        | `binary_div`, `binary_shift`                                                                   | Битовые операции       |

## 🧪 Тестирование

```bash
# Unit-тесты (~1000+ кейсов)
make test

# Покрытие кода (отчёт HTML)
make gcov_report
open report_lcov/index.html
```

## 📈 Пример использования

```c
#include "s21_decimal.h"

int main() {
    s21_decimal a, b, result;
    
    // 123.456789
    s21_from_float_to_decimal(123.456789f, &a);
    s21_from_float_to_decimal(10.0f, &b);
    
    s21_mul(a, b, &result);  // result = 1234.56789
    
    int int_result;
    s21_from_decimal_to_int(result, &int_result);  // 1234
}
```
***

**S21 Decimal** — **надёжная высокоточная арифметика** для финансовых расчётов и научных вычислений! 💰

*Разработано с ❤️ для School21 -  Precision matters!*
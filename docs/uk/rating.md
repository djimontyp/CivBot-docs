# Рейтингова система

!!! tip "Коротко про головне"
    Кожен гравець починає з 1000 очків рейтингу (⭐⭐) і може як набирати, так і втрачати очки залежно від результатів ігор. Ваш рейтинг визначає ваш ранг у системі.

## Як це працює?

У нашій системі у кожного гравця є два показники:

- **Рейтинг** — числове значення від 0 до нескінченності
- **Ранг** — рівень від 0 до 5, що визначається на основі рейтингу

### Ранги та рейтинг

| № рангу | Відображення | Рейтинг | 
|:--------|:------------:|:-------:|
| 5 | ⭐⭐⭐⭐⭐ | 1600+ |
| 4 | ⭐⭐⭐⭐ | 1400-1599 |
| 3 | ⭐⭐⭐ | 1200-1399 |
| 2 | ⭐⭐ | 1000-1199 |
| 1 | ⭐ | 800-999 |
| 0 | ⚡ | 0-799 |

### Як змінюється рейтинг?

Після кожної гри відбувається перерахунок рейтингу всіх учасників. На зміну впливають:

1. **Базові очки залежать від поточного рейтингу**
    - ⭐⭐⭐⭐/⭐⭐⭐⭐⭐ (1400+): ±25 очків
    - ⭐⭐⭐ (1200-1399): ±20 очків
    - ⭐⭐ (1000-1199): ±15 очків
    - ⭐/⚡ (до 999): ±10 очків

2. **Множник рангу переможця**
    - ⭐⭐⭐⭐⭐ (Ранг 5): ×0.6
    - ⭐⭐⭐⭐ (Ранг 4): ×0.8
    - ⭐⭐⭐ (Ранг 3): ×1.0
    - ⭐⭐ (Ранг 2): ×1.3
    - ⭐/⚡ (Ранг 1 та 0): ×1.5

!!! example "Приклади FFA ігор з різними переможцями"
    ### Приклад 1: Перемагає гравець високого рангу (множник ×0.8)

    | Місце | Переможець | Ранг | Рейтинг | Базові очки | Множник | Зміна | Новий рейтинг |
    |:-----:|:----------:|:----:|:-------:|:-----------:|:-------:|:-----:|:-------------:|
    | 1 | 👑 | ⭐⭐⭐⭐ | 1450 | +68 | ×0.8 | +68 | 1518 |
    | 2 | | ⭐⭐⭐⭐ | 1500 | -25 | ×0.8 | -20 | 1480 |
    | 3 | | ⭐⭐⭐ | 1350 | -20 | ×0.8 | -16 | 1334 |
    | 4 | | ⭐⭐ | 1150 | -15 | ×0.8 | -12 | 1138 |
    | 5 | | ⭐⭐ | 1100 | -15 | ×0.8 | -12 | 1088 |
    | 6 | | ⭐ | 950 | -10 | ×0.8 | -8 | 942 |

    ### Приклад 2: Перемагає новачок (множник ×1.5)

    | Місце | Переможець | Ранг | Рейтинг | Базові очки | Множник | Зміна | Новий рейтинг |
    |:-----:|:----------:|:----:|:-------:|:-----------:|:-------:|:-----:|:-------------:|
    | 1 | 👑 | ⭐ | 950 | +128 | ×1.5 | +128 | 1078 |
    | 2 | | ⭐⭐⭐⭐ | 1500 | -25 | ×1.5 | -38 | 1462 |
    | 3 | | ⭐⭐⭐ | 1350 | -20 | ×1.5 | -30 | 1320 |
    | 4 | | ⭐⭐ | 1150 | -15 | ×1.5 | -23 | 1127 |
    | 5 | | ⭐⭐ | 1100 | -15 | ×1.5 | -23 | 1077 |
    | 6 | | ⭐ | 980 | -10 | ×1.5 | -15 | 965 |

    Як видно з прикладів:
    
    - При перемозі ⭐⭐⭐⭐ (множник ×0.8) гравці втрачають менше очків
    - При перемозі ⭐ (множник ×1.5) втрати значно вищі
    - Базові очки залишаються тими ж, змінюється тільки множник
    - Переможець завжди отримує суму всіх втрат

### Додаткові множники

Для гравців з рейтингом 1400+ (⭐⭐⭐⭐ і вище) діє додатковий множник:
```
1.0 + (поточний_рейтинг - 1400) / 800
```

Це означає, що чим вищий ваш рейтинг після ⭐⭐⭐⭐, тим більше очків ви можете втратити при програші.
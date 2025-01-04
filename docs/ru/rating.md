# Рейтинговая система

!!! tip "Коротко о главном"
    Каждый игрок начинает с 1000 очков рейтинга (⭐⭐) и может как набирать, так и терять очки в зависимости от результатов игр. Ваш рейтинг определяет ваш ранг в системе.

## Как это работает?

В нашей системе у каждого игрока есть два показателя:

- **Рейтинг** — числовое значение от 0 до бесконечности
- **Ранг** — уровень от 0 до 5, определяемый на основе рейтинга

### Ранги и рейтинг

| № ранга | Отображение | Рейтинг | 
|:--------|:-----------:|:-------:|
| 5 | ⭐⭐⭐⭐⭐ | 1600+ |
| 4 | ⭐⭐⭐⭐ | 1400-1599 |
| 3 | ⭐⭐⭐ | 1200-1399 |
| 2 | ⭐⭐ | 1000-1199 |
| 1 | ⭐ | 800-999 |
| 0 | ⚡ | 0-799 |

### Как изменяется рейтинг?

После каждой игры происходит перерасчет рейтинга всех участников. На изменение влияют:

1. **Базовые очки зависят от текущего рейтинга**
    - ⭐⭐⭐⭐/⭐⭐⭐⭐⭐ (1400+): ±25 очков
    - ⭐⭐⭐ (1200-1399): ±20 очков
    - ⭐⭐ (1000-1199): ±15 очков
    - ⭐/⚡ (до 999): ±10 очков

2. **Множитель ранга победителя**
    - ⭐⭐⭐⭐⭐ (Ранг 5): ×0.6
    - ⭐⭐⭐⭐ (Ранг 4): ×0.8
    - ⭐⭐⭐ (Ранг 3): ×1.0
    - ⭐⭐ (Ранг 2): ×1.3
    - ⭐/⚡ (Ранг 1 и 0): ×1.5

!!! example "Примеры FFA игр с разными победителями"
    ### Пример 1: Побеждает игрок высокого ранга (множитель ×0.8)

    | Место | Победитель | Ранг | Рейтинг | Базовые очки | Множитель | Изменение | Новый рейтинг |
    |:-----:|:----------:|:----:|:-------:|:------------:|:---------:|:---------:|:-------------:|
    | 1 | 👑 | ⭐⭐⭐⭐ | 1450 | +68 | ×0.8 | +68 | 1518 |
    | 2 | | ⭐⭐⭐⭐ | 1500 | -25 | ×0.8 | -20 | 1480 |
    | 3 | | ⭐⭐⭐ | 1350 | -20 | ×0.8 | -16 | 1334 |
    | 4 | | ⭐⭐ | 1150 | -15 | ×0.8 | -12 | 1138 |
    | 5 | | ⭐⭐ | 1100 | -15 | ×0.8 | -12 | 1088 |
    | 6 | | ⭐ | 950 | -10 | ×0.8 | -8 | 942 |

    ### Пример 2: Побеждает новичок (множитель ×1.5)

    | Место | Победитель | Ранг | Рейтинг | Базовые очки | Множитель | Изменение | Новый рейтинг |
    |:-----:|:----------:|:----:|:-------:|:------------:|:---------:|:---------:|:-------------:|
    | 1 | 👑 | ⭐ | 950 | +128 | ×1.5 | +128 | 1078 |
    | 2 | | ⭐⭐⭐⭐ | 1500 | -25 | ×1.5 | -38 | 1462 |
    | 3 | | ⭐⭐⭐ | 1350 | -20 | ×1.5 | -30 | 1320 |
    | 4 | | ⭐⭐ | 1150 | -15 | ×1.5 | -23 | 1127 |
    | 5 | | ⭐⭐ | 1100 | -15 | ×1.5 | -23 | 1077 |
    | 6 | | ⭐ | 980 | -10 | ×1.5 | -15 | 965 |

    Как видно из примеров:
    
    - При победе ⭐⭐⭐⭐ (множитель ×0.8) игроки теряют меньше очков
    - При победе ⭐ (множитель ×1.5) потери значительно выше
    - Базовые очки остаются теми же, меняется только множитель
    - Победитель всегда получает сумму всех потерь

### Дополнительные множители

Для игроков с рейтингом 1400+ (⭐⭐⭐⭐ и выше) действует дополнительный множитель:
```
1.0 + (текущий_рейтинг - 1400) / 800
```

Это означает, что чем выше ваш рейтинг после ⭐⭐⭐⭐, тем больше очков вы можете потерять при проигрыше.
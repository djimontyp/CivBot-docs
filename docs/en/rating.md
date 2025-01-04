# Rating System

!!! tip "Key Points"
    Each player starts with 1000 rating points (⭐⭐) and can gain or lose points based on game results. Your rating determines your rank in the system.

## How It Works

In our system, each player has two indicators:

- **Rating** — a numerical value from 0 to infinity
- **Rank** — a level from 0 to 5, determined by your rating

### Ranks and Rating

| Rank № | Display | Rating | 
|:-------|:-------:|:------:|
| 5 | ⭐⭐⭐⭐⭐ | 1600+ |
| 4 | ⭐⭐⭐⭐ | 1400-1599 |
| 3 | ⭐⭐⭐ | 1200-1399 |
| 2 | ⭐⭐ | 1000-1199 |
| 1 | ⭐ | 800-999 |
| 0 | ⚡ | 0-799 |

### How Rating Changes

After each game, the rating of all participants is recalculated. The changes are affected by:

1. **Base points depend on current rating**
    - ⭐⭐⭐⭐/⭐⭐⭐⭐⭐ (1400+): ±25 points
    - ⭐⭐⭐ (1200-1399): ±20 points
    - ⭐⭐ (1000-1199): ±15 points
    - ⭐/⚡ (up to 999): ±10 points

2. **Winner's rank multiplier**
    - ⭐⭐⭐⭐⭐ (Rank 5): ×0.6
    - ⭐⭐⭐⭐ (Rank 4): ×0.8
    - ⭐⭐⭐ (Rank 3): ×1.0
    - ⭐⭐ (Rank 2): ×1.3
    - ⭐/⚡ (Rank 1 and 0): ×1.5

!!! example "FFA Game Examples with Different Winners"
    ### Example 1: High-rank player wins (multiplier ×0.8)

    | Place | Winner | Rank | Rating | Base Points | Multiplier | Change | New Rating |
    |:-----:|:------:|:----:|:------:|:-----------:|:----------:|:------:|:----------:|
    | 1 | 👑 | ⭐⭐⭐⭐ | 1450 | +68 | ×0.8 | +68 | 1518 |
    | 2 | | ⭐⭐⭐⭐ | 1500 | -25 | ×0.8 | -20 | 1480 |
    | 3 | | ⭐⭐⭐ | 1350 | -20 | ×0.8 | -16 | 1334 |
    | 4 | | ⭐⭐ | 1150 | -15 | ×0.8 | -12 | 1138 |
    | 5 | | ⭐⭐ | 1100 | -15 | ×0.8 | -12 | 1088 |
    | 6 | | ⭐ | 950 | -10 | ×0.8 | -8 | 942 |

    ### Example 2: Newcomer wins (multiplier ×1.5)

    | Place | Winner | Rank | Rating | Base Points | Multiplier | Change | New Rating |
    |:-----:|:------:|:----:|:------:|:-----------:|:----------:|:------:|:----------:|
    | 1 | 👑 | ⭐ | 950 | +128 | ×1.5 | +128 | 1078 |
    | 2 | | ⭐⭐⭐⭐ | 1500 | -25 | ×1.5 | -38 | 1462 |
    | 3 | | ⭐⭐⭐ | 1350 | -20 | ×1.5 | -30 | 1320 |
    | 4 | | ⭐⭐ | 1150 | -15 | ×1.5 | -23 | 1127 |
    | 5 | | ⭐⭐ | 1100 | -15 | ×1.5 | -23 | 1077 |
    | 6 | | ⭐ | 980 | -10 | ×1.5 | -15 | 965 |

    As seen from the examples:
    
    - When ⭐⭐⭐⭐ wins (multiplier ×0.8), players lose fewer points
    - When ⭐ wins (multiplier ×1.5), losses are significantly higher
    - Base points remain the same, only the multiplier changes
    - The winner always receives the sum of all losses

### Additional Multipliers

For players with rating 1400+ (⭐⭐⭐⭐ and above), an additional multiplier applies:
```
1.0 + (current_rating - 1400) / 800
```

This means that the higher your rating after ⭐⭐⭐⭐, the more points you can lose when defeated.
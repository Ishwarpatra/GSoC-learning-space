---
title: Continuous Space Predator-Prey
authors:
  - Ishwarpatra
domain:
  - biology
  - population-dynamics
complexity: intermediate
mesa_version_min: "4.0"
status: incubator
keywords: [continuous space, lotka-volterra, carrying capacity, solara]
---

# Continuous Space Predator-Prey Model

## Summary
A Mesa 4.0 model of predators and prey on `ContinuousSpace` with energy, aging, and local reproduction limits.

- Prey live up to 40 steps, require nearby mates, and stop reproducing when crowding is high.
- Predators live up to 60 steps, use an energy budget, hunt prey at radius 4.0, and reproduce only when energy > 30.
- Uses modern `agents.shuffle_do()` and automatic agent IDs for stable, shuffle-based scheduling.

## Core mechanics

Prey are fast, regularly reproduce under low density, and age out. Predators are stronger, lose 1 energy each step, gain energy by eating prey, and starve at 0.

Population behavior matches Lotka-Volterra cycles:

- prey rise first, predator rise after, prey fall, predator fall, repeat.

## Run the model

### Interactive UI (Solara)

```bash
solara run app.py
```

Then control sliders for initial populations and reproduction parameters.

### Headless mode

```bash
python run.py
```

## Install

```bash
pip install -r requirements.txt
pip install solara
```

## Configuration

| Parameter | Default | Effect |
|-----------|---------|-------|
| `width` | 100 | continuous space width |
| `height` | 100 | continuous space height |
| `initial_prey` | 100 | starting prey count |
| `initial_predators` | 20 | starting predator count |
| `prey_reproduce` | 0.04 | prey reproduction probability per step |
| `predator_reproduce` | 0.05 | predator reproduction probability per step |
| `predator_gain_from_food` | 20 | energy gained per prey eaten |

## Expected output

- spatial map: blue prey, red predators
- population chart: classic predator-prey oscillations (red trails blue)

## Code style

```bash
ruff check . --fix
ruff format .
```

## Files

- `model.py` – main Mesa model class
- `agents.py` – Prey and Predator definitions
- `app.py` – Solara UI definition
- `run.py` – headless run script


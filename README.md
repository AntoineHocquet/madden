# Madden Live Win-Probability Model Validation

A case study comparing two predictive models for live win probabilities in **Madden** (American football video game) matches.

## Objective

Analyze play-by-play data from 233 Madden matches to determine which of two models — **Model 1** or **Model 2** — produces more accurate and reliable live win probabilities, and provide a clear recommendation backed by data.

## Dataset

`case_study_dataset.csv` — 233 matches, one row per play (end-of-play game state snapshot).

| Column | Description |
|---|---|
| `match_id` | Unique game identifier |
| `play_id` | Play sequence within a game |
| `home_player` / `away_player` | Player identifiers |
| `quarter` | Current quarter (1–4) |
| `remaining_quarter_time` | Seconds remaining in the quarter |
| `score_home` / `score_away` | Score at time of play |
| `ball_possession` | Team on offense (`home` or `away`) |
| `down` | Current down (1–4) |
| `first_down_distance` | Yards needed for a new set of downs |
| `yards_to_endzone` | Yards to the opponent's goal line |
| `timeouts_home` / `timeouts_away` | Timeouts remaining (max 3 per half) |
| `prematch_home_prob` | Opening win probability from a prematch expert model |
| `home_prob_model_1` / `away_prob_model_1` | Live win probabilities from Model 1 |
| `home_prob_model_2` / `away_prob_model_2` | Live win probabilities from Model 2 |

## Approach

The analysis covers:

- **Calibration** — are the predicted probabilities well-calibrated against actual outcomes?
- **Discrimination** — do the models correctly rank outcomes (AUC/Brier score)?
- **Temporal consistency** — do probabilities evolve smoothly and sensibly over the course of a game?
- **Comparison against the prematch baseline** — how much do the live models improve over the opening prediction?

## Structure

```
.
├── README.md
├── case_study_dataset.csv
└── analysis.ipynb        # Main notebook with code, plots, and findings
```

## Usage

```bash
pip install -r requirements.txt
jupyter notebook analysis.ipynb
```

## Results

See `analysis.ipynb` for the full write-up, plots, and final recommendation.

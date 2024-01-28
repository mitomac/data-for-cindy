# Making the data tidy

Currenlty, the data is in a  wide format, the data looks like this:

| Week | 526  | 527  | 529  | 530  | ... | 550  |
|------|------|------|------|------|-----|------|
| 1    | 3.4  | 2.9  | 3.1  | 2.7  | ... | x.xx |
| 2    | 2.32 | 1.2  | 2.1  | 4.2  | ... | x.xx |
| 3    | 4.3  | 2.8  | 4.9  | 6.9  | ... | x.xx |
| 4    | 3.4  | 3.2  | 2.85 | 3.7  | ... | x.xx |
| ...  | ...  | ...  | ...  | ...  | ... | ...  |

In the wide format, each row represents a week, and each column (except for the `Week` column) represents a different individual or measurement.

We want to convert the data to long format using `pivot_longer()`, so the data will look like this:

| Week | Individual | Value |
|------|------------|-------|
| 1    | 526        | 3.4   |
| 1    | 527        | 2.9   |
| 1    | 529        | 3.1   |
| 1    | 530        | 2.7   |
| ...  | ...        | ...   |
| 2    | 526        | 2.32  |
| 2    | 527        | 1.2   |
| 2    | 529        | 2.1   |
| 2    | 530        | 4.2   |
| ...  | ...        | ...   |
| 3    | 526        | 4.3   |
| ...  | ...        | ...   |
| 4    | 550        | x.xx  |
| ...  | ...        | ...   |

In the long format:
- Each row represents a single observation for a specific week and individual.
- The `Week` column indicates the week number.
- The `Individual` column is created from the names of the original columns (e.g., `526`, `527`, etc.), representing the individual or measurement.
- The `Value` column contains the data values corresponding to each week and individual.

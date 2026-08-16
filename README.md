# Student Performance Analysis: The Impact of Variables and Demographics

**Author:** Mansi Kumar
**Course:** CS 544 — Foundations of Analytics with R

An exploratory and inferential analysis of a 4,000-student dataset, examining how study habits, tutoring, attendance, and parental education relate to exam performance — with a dedicated demonstration of the Central Limit Theorem via repeated sampling, and a comparison of three probability sampling methods.

## Project structure

```
nicoleivant-attachments/
├── CS544FinalProject_Kumar.Rmd    # R Markdown source: all analysis, code, and narrative
├── CS544FinalProject_Kumar.html   # Rendered/knitted report (open in a browser)
├── SAP-4000 (1).csv               # Source dataset (4,000 student records)
└── README.md
```

## Dataset

**File:** `SAP-4000 (1).csv` — 4,000 rows, 7 columns, no missing values.

| Column | Description | Values |
|---|---|---|
| `Gender` | Student gender | Male, Female |
| `HoursStudied/Week` | Self-reported weekly study hours | numeric |
| `Tutoring` | Whether the student received tutoring | Yes, No |
| `Region` | Student's home region | Urban, Rural |
| `Attendance(%)` | Class attendance rate | numeric (0–100) |
| `Parent Education` | Highest education level of parent/guardian | None, Primary, Secondary, Tertiary |
| `Exam_Score` | Final exam score (target variable) | numeric (0–100) |

## Analysis

The report (`CS544FinalProject_Kumar.Rmd`, rendered in `CS544FinalProject_Kumar.html`) covers:

1. **Categorical variable analysis** — distribution of students by parent education level.
2. **Numerical variable analysis** — distribution of weekly study hours.
3. **Multivariable analysis** — study hours vs. exam score, colored by tutoring status.
4. **Exam score distribution** — population mean (71.11) and standard deviation (16.75).
5. **Central Limit Theorem** — sampling distributions of the mean at n = 10, 20, 40, 60, showing the distribution narrowing and approaching normality as sample size increases.
6. **Sampling methods** — simple random sampling (SRSWR), systematic sampling (unequal probabilities via `Exam_Score`), and proportional stratified sampling, compared against the subset mean.
7. **Data wrangling** — average exam score by gender, and by attendance group (<60% vs. >90%).

## Key findings

- Positive correlation between weekly study hours and exam score; tutored students outperform non-tutored students at the same study-hour level.
- Higher parental education levels are associated with better student performance.
- Students with >90% attendance averaged **76.54**, vs. **65.31** for students with <60% attendance.
- Average exam score by gender was similar: Female 71.94, Male 70.24.
- Sampling distributions of the mean confirm the Central Limit Theorem: as sample size increases (n = 10 → 60), the distribution becomes narrower, taller, and more bell-shaped, with standard deviation shrinking toward 2.14 and the mean converging on the population mean.
- Among the three sampling methods tested, **stratified sampling** produced the mean closest to the true subset mean, indicating the most reliable representation.

## How to reproduce

Open `CS544FinalProject_Kumar.Rmd` in RStudio with `SAP-4000 (1).csv` in the same directory, and knit to HTML. Requires the R packages: `plotly`, `sampling`, `tidyverse`, `knitr`.

# Data Analysis & Visualization Portfolio

Two exploratory data analysis projects built in Python using Jupyter notebooks.  
Each notebook follows a consistent workflow: **Data Cleaning → EDA → Key Questions → Findings & Conclusion**.

---

## Projects

### 1. Smartphone Usage and Addiction Analysis

**Notebook:** [`IPV/smartphone_analysis.ipynb`](IPV/smartphone_analysis.ipynb)  
**Dataset:** 7,500 survey records · 16 columns  
**Source columns include:** age, gender, daily screen time, social media hours, gaming hours, sleep hours, notifications per day, app opens per day, stress level, addiction level

#### What I did
- Loaded and inspected the dataset (shape, dtypes, null counts, descriptive statistics)
- Checked for missing values and duplicates; performed targeted cleaning for a partially populated categorical column
- Created a **`primary_usage` feature** (engineering a new variable by comparing `gaming_hours` vs `social_media_hours`) to answer a question the raw data could not directly address
- Created a **`low_sleep` binary flag** (sleep < 6 hours) to convert a continuous relationship question into a group comparison
- Ran a **correlation heatmap** across all numeric variables before the key-question phase to form data-driven hypotheses before plotting
- Built targeted visualisations for each question (histogram, scatter plots, box plots, grouped bar charts), with written justification for each chart type choice

#### Key questions answered
| # | Question | Chart type used |
|---|----------|-----------------|
| Q1 | What is the most common daily screen-time range? | Histogram |
| Q2 | Do more notifications / screen time lead to less sleep and more stress? | Scatter plots + box plot |
| Q3 | Do males and females show different addiction levels or primary usage types? | Grouped count plots |
| Q4 | Is there a social media usage level that predicts < 6 hours of sleep? | Box plot + histogram by group |

#### Honest findings
- Most respondents fall in the **6–8 hours/day** screen-time range (roughly 40–50 % of waking hours).
- The link between screen time / notifications and sleep is **present but weak** — stress emerged as a stronger mediator than raw screen time, which is an honest null-ish result rather than a forced conclusion.
- Addiction-level distribution was **broadly similar across genders**; the clearer gender split was in usage type (males → gaming, females → social media).
- Social media hours alone were **not a clean predictor of sleep deprivation** — the distributions of low-sleep vs normal-sleep groups overlapped considerably.

---

### 2. Philippine Dengue Cases Analysis (2016–2020)

**Notebook:** [`IPV/ph_dengue_analysis.ipynb`](IPV/ph_dengue_analysis.ipynb)  
**Dataset:** 1,020 records · 17 regions × 12 months × 5 years  
**Columns:** Region, Year, Month, Dengue\_Cases, Dengue\_Deaths

#### What I did
- Inspected dtypes, null counts, and duplicates — confirmed the dataset was clean with no missing values or duplicate rows
- Engineered a **`Month_Num` column** by mapping month names to integers for correct chronological sorting
- Computed a **`CFR` (Case Fatality Rate)** derived column (`deaths / cases × 100`) to detect outlier months where deaths were disproportionately high
- Built annual and monthly aggregate bar charts, a regional horizontal bar chart, and a **region × year heatmap** for EDA
- Framed five specific analytical questions and built dedicated visualisations for each

#### Key questions answered
| # | Question | Chart type used |
|---|----------|-----------------|
| Q1 | Which months are peak dengue season, and was 2019 significantly higher? | Multi-line chart (one line per year) |
| Q2 | Top 3 regions by total cases; how does Region IV-A compare to NCR? | Highlighted bar chart |
| Q3 | Did cases migrate or intensify across regions? (Region VI vs Region I) | Multi-line chart + annotated area chart |
| Q4 | Does a higher case count always mean more deaths? | Scatter plot coloured by CFR |
| Q5 | In 2019, what share did the top 5 regions contribute? | Calculated percentage + pie/bar breakdown |

#### Honest findings
- Peak dengue season is consistently **July–October**, aligning with the Philippine monsoon.
- **2019 was a national outbreak year** — cases spiked across virtually every region, not just one area.
- **Region IV-A (CALABARZON)** had the highest cumulative cases — roughly 2–3× more than NCR despite NCR being more densely populated, suggesting higher reporting or case density.
- Higher case counts do **not always correlate with higher deaths**; some smaller regions had disproportionately high CFR values, pointing to possible healthcare-access or detection-timing issues.
- In 2019, the **top 5 most affected regions accounted for over 50 % of national cases**, showing that dengue burden is geographically concentrated.

---

## Skills Demonstrated

| Area | Details |
|------|---------|
| **Python data stack** | `pandas`, `matplotlib`, `seaborn` |
| **Data cleaning** | Null/duplicate checks, dtype inspection, range validation |
| **Feature engineering** | Derived columns (`Month_Num`, `CFR`, `primary_usage`, `low_sleep`) from raw data to answer specific questions |
| **Exploratory data analysis** | Descriptive statistics, correlation matrices, distribution checks before hypothesis formation |
| **Data visualisation** | Histograms, scatter plots, box plots, bar charts, horizontal bar charts, heatmaps, multi-line time-series charts — with written justification for each chart type |
| **Analytical thinking** | Framing specific, answerable questions; interpreting weak signals honestly rather than overstating results |
| **Communication** | Each notebook is written educationally — every step includes reasoning in markdown, not just code |

---

## Repository Structure

```
IPV/
├── smartphone_analysis.ipynb               # Smartphone & addiction EDA
├── Smartphone_Usage_And_Addiction_Analysis_7500_Rows.csv
├── ph_dengue_analysis.ipynb                # Philippine dengue EDA
└── ph_dengue_cases2016-2020.csv
```

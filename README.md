# Event Boundaries and Recognition Memory

### An Analysis using the Mnemonic Similarity Task (MST)

**Authors:** Gargie Tambe (2022111008), Navdha Bansal (2022101055), Paridhi Jain (2022101119)

---

## Overview

This project investigates how event boundaries and stimulus similarity influence recognition memory, using behavioral data from the Mnemonic Similarity Task (MST). Participants' responses are analyzed to evaluate recognition memory (REC) and mnemonic discrimination (LDI) across three experimental conditions.

---

## Repository Structure

```
.
├── code.ipynb                  # Main analysis notebook
├── docs/
│   └── Report.pdf              # Full project report
├── MST_Data/
│   ├── Both_item_task/         # Condition: Both items + task
│   │   ├── both_data/          # Per-participant encoding & test CSVs
│   │   ├── Set6 bins.txt
│   │   └── SetScC bins.txt
│   ├── item_only/              # Condition: Item only
│   │   ├── item_only_data/     # Per-participant encoding & test CSVs
│   │   ├── scenes_mapping.txt
│   │   ├── Set6 bins.txt
│   │   └── SetScC bins.txt
│   └── task_only/              # Condition: Task only
│       ├── task_only_data/     # Per-participant encoding & test CSVs
│       └── Set6 bins_ob.txt
└── README.md
```

---

## Experimental Design

**Participants:** 160 total across three conditions:

- `item_only` (n = 56)
- `both` (n = 51)
- `task_only` (n = 53)

**Encoding Phase:** Participants viewed sequences of images organized into 40 events (7 items each). Items were labeled by position:

- Item 1 → Pre-boundary
- Items 2–6 → Mid-event
- Item 7 → Post-boundary

A semantic judgment task ("Will this fit in a shoebox?") ensured active encoding.

**Test Phase:** Participants classified images as:

- **Old (o)** – exact repeat
- **Similar (s)** – visually similar but not identical
- **New (n)** – novel image

The test set contained 60 targets, 60 lures, and 30 foils. Lures were grouped into 5 similarity bins (Bin 1 = most similar, Bin 5 = least similar).

---

## Key Metrics

**Recognition Memory Index (REC)**

```
REC = P(old | target) − P(old | foil)
```

**Lure Discrimination Index (LDI)**

```
LDI = P(similar | lure) − P(similar | foil)
```

---

## Data Format

Each participant contributes two CSV files per condition:

- `{ID}_MST_task_{datetime}.csv` — encoding phase responses
- `{ID}_MST_test_{datetime}.csv` — recognition test responses

Stimulus types are identified from filenames:

- Targets → filenames ending in `a.jpg`
- Lures → filenames ending in `b.jpg`
- Foils → filenames starting with `foil/`

---

## Analysis (`code.ipynb`)

The notebook covers:

1. **Data loading & preprocessing** across all three conditions
2. **Exploratory Data Analysis** — response distributions, REC/LDI by condition, RT distributions
3. **Hypothesis 1** — One-sample t-test: REC and LDI > 0 (normality checked via Shapiro-Wilk & Q-Q plots)
4. **Hypothesis 2** — Kruskal-Wallis test + Dunn post-hoc: discrimination performance across lure similarity bins

### Key Findings

- Mean REC ≈ 0.25, Mean LDI ≈ 0.17 — both significantly above chance
- Discrimination improves as lure similarity decreases (graded pattern separation)
- "Similar" responses had slightly longer reaction times, consistent with additional cognitive processing

---

## References

1. Event Segmentation Theory — https://pmc.ncbi.nlm.nih.gov/articles/PMC2852534/
2. Mnemonic Similarity Task — https://pmc.ncbi.nlm.nih.gov/articles/PMC3675184/
3. Hippocampal Pattern Separation — https://pmc.ncbi.nlm.nih.gov/articles/PMC3183227/

---

## Links

- **Dataset:** [Google Drive](https://drive.google.com/drive/folders/10hYwuHbipr78Drb9QN3WSdT-Upspe-wL)
- **Code:** [GitHub](https://github.com/Navdha1801/BRSM_project_phase1/tree/main)

---

## Contributions

| Member        | Contribution                |
| ------------- | --------------------------- |
| Navdha Bansal | Visualizations and Analysis |
| Paridhi Jain  | Hypothesis 1 and Analysis   |
| Gargie Tambe  | Hypothesis 2 and Analysis   |

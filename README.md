# Anomaly detection in marine ecology

Supplementary data and code for the systematic literature review:

**Anomaly Detection in Marine Ecology: A Survey, Best Practices, and Future Trends**
Nicole Oyetunji, Marcellin Atemkeng, Taryn S. Murray, Siphendulwe Zaza.


## What this repository contains

This repository holds the records retrieved from each database, the deduplicated screening workbook, the eligibility criteria, the rubric used to evaluate methodological rigour, the two raters' detailed scores, and the code used to quantify agreement between the raters. Together these allow the search, screening and evaluation to be validated and the inter-rater analysis to be reproduced.

```
.
├── README.md
├── data/
│   ├── 01_search_results/
│   │   ├── google_scholar.xlsx
│   │   ├── web_of_science.xlsx
│   │   ├── scopus.xlsx
│   │   └── pubmed.xlsx
│   ├── 02_screening/
│   │   └── screening_deduplicated.xlsx
│   └── 03_criteria/
│       └── inclusion_exclusion_criteria.md
├── rubric/
│   └── methodological_rigour_rubric.pdf
├── rater_scores/
│   ├── rater1_scores.pdf
│   └── rater2_scores.pdf
└── code/
    └── inter_rater_reliability.ipynb
```

## Search

Four databases were last searched on 29 September 2026.

| Database | Search string | Records retrieved |
|---|---|---|
| Google Scholar | `"anomaly detection" AND "marine ecology" -maritime` | 309 |
| Web of Science | `ALL=(("anomaly detection") AND "marine" AND ("ecology" OR "ecological"))` | 16 |
| Scopus | `TITLE-ABS-KEY("anomaly detection" AND "marine" AND ("ecology" OR "ecological"))` | 10 |
| PubMed | `("anomaly detection" AND "marine" AND ("ecology" OR "ecological"))` | 3 |
| **Total** | | **338** |

The file for each database in `data/01_search_results/` contains the records exactly as retrieved, before any deduplication.

## Deduplication

Duplicates were removed in two stages, using Excel and then manual checking. Duplicates were identified in Excel by matching standardised titles, and the records were then checked manually to remove duplicates that the matching had missed because the same title was recorded differently across databases, for example truncated, abbreviated, or with variant spelling or punctuation. This left **318** unique records, which are listed together in `data/02_screening/screening_deduplicated.xlsx`.


## Screening

Screening followed PRISMA guidelines and had two stages.

| Stage | Records | Outcome |
|---|---|---|
| Title and abstract screening | 318 | 263 excluded, 55 taken forward |
| Full-text screening | 55 | 40 excluded, 15 included |

Reasons for exclusion at the full-text stage: article not accessible, not in English, no marine ecological focus, and anomaly detection not applied.

The 15 included studies were published between 2012 and 2026.

### The screening workbook

`screening_deduplicated.xlsx` contains all 318 deduplicated records from the four databases. It has a column for the title and abstract decision and one for the full-text decision. Records that passed title and abstract screening are labelled "Screen further", records which failed are labelled "Excluded" along with a reason. Colour coding is used throughout, with **red** marking excluded records and **green** marking included records.

## Eligibility criteria

The same criteria were applied at both screening stages and are also provided in `data/03_criteria/inclusion_exclusion_criteria.md`.

| Inclusion criteria | Exclusion criteria |
|---|---|
| 1. The publication is in English. | 1. The article is not written in English. |
| 2. The research focuses on anomaly detection in marine ecology, specifically detecting anomalies in (a) organism behaviour or movement patterns, (b) biological or ecological events, or (c) biological or ecological data quality. | 2. The focus is not on biological or ecological anomalies in marine systems (for example, studies focused solely on physical habitat characterisation, geophysical features, or maritime operations without ecological context). |
| 3. The research objectives are explicitly stated, and the statistical analysis is suitable for addressing the study's research questions and objectives. | 3. Anomaly detection methods are not applied or evaluated. |
| 4. Anomaly detection methods are applied and evaluated, with the experimental design outlined and results presented. | 4. The research objectives are not clearly defined. |
| | 5. The research does not include a defined methodology for anomaly detection, or lacks sufficient detail in its experimental design. |
| | 6. The statistical analysis and conclusions are not robust or reproducible. |

## Methodological rigour  assessment

Each of the 15 included studies was scored independently by two raters on five criteria: detection performance, theoretical foundation, computational efficiency, interpretability and ecological relevance. Each criterion is scored from 0 (very poor) to 3 (excellent), using the descriptors in `rubric/methodological_rigour_rubric.pdf`. The detailed scores, with a written justification for each, are in `rater_scores/`.

## Inter-rater analysis

`code/inter_rater_reliability.ipynb` reads the paired scores, which are defined at the top of the notebook, and computes weighted and unweighted Cohen's kappa, exact agreement, mean absolute difference and Spearman correlation for each criterion and overall. It also calculates the mean score of the two raters on each criterion for every methodological paradigm (statistical, machine learning, deep learning and the hybrid categories), and produces the agreement and average score figures reported in the manuscript. Kappa is undefined for ecological relevance, because both raters scored every study 3 out of 3.

To run it:

```
pip install numpy scipy scikit-learn matplotlib jupyter
jupyter notebook code/inter_rater_reliability.ipynb
```


Bibliographic records in `data/01_search_results/` were exported from commercial and public databases and remain subject to those databases' terms. Full texts of the reviewed studies are not redistributed here.



## Contact

[Nicole Oyetunji, n.oyetunji@gmail.com]

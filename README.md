# Route Roulette — Hack4Rail 2026

**Budget allocation analysis for the Swiss Jura railway network (SBB)**

This project explores how to allocate infrastructure investment budgets across railway sections (Strecken) in the Jura sub-network, using the MIAM model outputs: asset condition scores, lifecycle data, renewal-risk (ER) demand, and scheduled investment costs (IR).

## Background

<p align="center">
  <img alt="Hack4Rail Logo" src="img/hack4rail-logo.jpg" width="400"/>
</p>

This project has been initiated during the [Hack4Rail 2026](https://hack4rail.org/), a joint hackathon organised by the railway companies SBB, ÖBB, and DB in partnership with the OpenRail Association.

## Repository structure

```
route-roulette/
├── data/                          # ← not committed (add your data here locally)
│   └── version_limited_ressources/
│       └── C200/                  # geo-resolution: ~200 m asset chunks
│       ├── Teilnetz_Invest_Resultate_V24_1300MCHF_Chunk200.xlsx
│       ├── Auswertung_ER_2025_V22_002_Fokus_Top_Hauptstrecken_VTHP50_1300MCHF_AB_Chunk200.xlsx
│       ├── Auswertung_IR_2025_V22_002_Fokus_Top_Hauptstrecken_VTHP50_1300MCHF_AB_Chunk200.xlsx
│       ├── Auswertung_Gesamtmittel_2025_V22_002_Fokus_Top_Hauptstrecken_VTHP_50_1300MCHF_AB_Chunk200.xlsx
│       ├── 2025_Dev_Gestamtsystem_V24_VTHP50_1300MCHF_Chunk200.xlsx
│       ├── 2025_Dev_Gestamtsystem_V24_Streckenkategorie_VTHP50_1300MCHF_Chunk200.xlsx
│       ├── Res_V24_AB1300_25to50_Chunk200_Jura_Schema   # PostgreSQL schema — Jura sub-network result tables
│       └── Res_V24_AB1300_25to50_Chunk200_Schema        # PostgreSQL schema — full MIAM database (67 tables)
├── route_roulette_analysis.ipynb  # main EDA notebook: loads data, section-level summary & visuals
├── pyproject.toml                 # Poetry dependency manifest
├── poetry.lock                    # locked dependency versions
└── .gitignore
```

> **Note:** the `data/` folder is excluded from version control (see `.gitignore`).
> Place the provided data files under `data/version_limited_ressources/C200/` before running the notebook.

## Install

### Prerequisites

- Python 3.12+
- [Poetry](https://python-poetry.org/) (`pip install poetry` or follow the [official guide](https://python-poetry.org/docs/#installation))

### Setup

```bash
git clone https://github.com/OpenRail-Playground/route-roulette.git
cd route-roulette

# Install dependencies into a local .venv
poetry config virtualenvs.in-project true
poetry install

# Launch Jupyter
poetry run jupyter notebook route_roulette_analysis.ipynb
```

Then place the data files under `data/version_limited_ressources/C200/` and run all cells.

## License

<!-- If you decide for another license, please change it here, and exchange the LICENSE file -->

The content of this repository is licensed under the [Apache 2.0 license](LICENSE).

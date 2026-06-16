# Programming for Economists — Group 2_5

Quantifying a Social Problem: GDP Growth and Unemployment in the Netherlands and Western Europe.

## Project description

This project analyses the relationship between GDP growth and unemployment in the Netherlands and Western Europe over the period 2015–2025, using annual data from Eurostat. We focus on three things: the time-series relationship between GDP growth and unemployment in the Netherlands (an empirical look at Okun's Law), the spatial variation in unemployment across Western Europe in 2020, and the gap between total and youth (ages 15–24) unemployment. The full report is produced from `betaversion.Rmd`, which loads the raw Eurostat extracts from the `data/` folder and regenerates every figure on knit.

## Data sources

All data was downloaded from Eurostat:

- Real GDP growth rate (table `tec00115`): https://ec.europa.eu/eurostat/databrowser/view/tec00115/default/table?lang=en
- Total unemployment rate (table `tesem120`): https://ec.europa.eu/eurostat/databrowser/view/tesem120/default/table?lang=en
- Youth unemployment, ages 15–24 (table `tipslm80`): https://ec.europa.eu/eurostat/databrowser/view/tipslm80/default/table?lang=en

The raw CSV extracts are stored in the `data/` folder of this repository, so the report runs without re-downloading anything.

## How to reproduce

1. Clone the repository:
   ```
   git clone https://github.com/dcdavidcraveiro-arch/PFE_Group_Project.git
   ```
2. Open `ProgrForEconom.Rproj` in RStudio (this sets the working directory to the project root automatically).
3. Make sure the three Eurostat CSVs are in the `data/` folder:
   - `data/raw_gdp.csv`
   - `data/raw_unemployment_sex.csv`
   - `data/raw_unemployment_youth.csv`
4. Install the required R packages:
   ```r
   install.packages(c("tidyverse", "maps", "tinytex"))
   tinytex::install_tinytex()  # only needed once, for PDF output
   ```
5. Open `betaversion.Rmd` in RStudio and click **Knit** (or run `rmarkdown::render("betaversion.Rmd")`). The PDF report will be produced as `betaversion.pdf`.

## Repository structure

```
PFE_Group_Project/
├── betaversion.Rmd            # main report (knit this)
├── betaversion.pdf            # knitted output
├── Template_Assignment.Rmd    # original course template (reference)
├── Template_Assignment.pdf
├── references.bib             # bibliography
├── apa.csl                    # APA citation style
├── ProgrForEconom.Rproj       # RStudio project file
├── data/                      # raw Eurostat extracts
│   ├── raw_gdp.csv
│   ├── raw_unemployment_sex.csv
│   └── raw_unemployment_youth.csv
├── drafts/                    # earlier drafts and experiments
├── renv/                      # renv project library
└── renv.lock                  # locked package versions
```

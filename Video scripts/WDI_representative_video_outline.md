# WDI Representative Video Outline

## Video Title

**World Bank WDI Data Analysis with Python: From Raw Data to Panel Dataset**

## Video Purpose

This video is a representative teaching demo for the **Big Data Analysis with Python** portfolio. It shows how to turn raw World Bank World Development Indicators (WDI) data into a clean country-year panel dataset that can be used for visualisation, regression, sustainability indicators and policy analysis.

The video should demonstrate not only Python syntax, but also the teaching logic behind applied data analysis: understanding the dataset, inspecting structure, selecting relevant information, reshaping data, checking missing values and exporting a reusable output.

## Target Audience

- Undergraduate or master's students learning applied data analysis
- Early-stage researchers working with development or economic data
- Viewers interested in Python, pandas, WDI data and panel datasets
- Employers or collaborators evaluating online teaching, data education and research training capability

## Target Length

**8-12 minutes**

Suggested pacing:

- 0:00-0:45 Hook
- 0:45-1:30 Roadmap
- 1:30-3:00 Dataset introduction
- 3:00-5:00 Read and inspect data
- 5:00-7:30 Select and clean data
- 7:30-9:30 Reshape into panel format
- 9:30-10:45 Check missing values and export
- 10:45-12:00 Recap and GitHub link

## Learning Objectives

By the end of the video, viewers should be able to:

1. Explain why raw WDI data is not immediately analysis-ready.
2. Use pandas to read and inspect a WDI dataset.
3. Select relevant countries, indicators and year columns.
4. Reshape wide-format WDI data into long and panel formats.
5. Check missing values and export a cleaned dataset for later analysis.

## Dataset and Tools

- Dataset: World Bank World Development Indicators (WDI), teaching subset
- Repository: `Big-Data-Analysis-2025`
- Notebook: `lectures/01_wdi_data_analysis/WDI_data_analysis.ipynb`
- Tools: Python, pandas, Jupyter Notebook or Google Colab

## Opening Hook

**What to say**

Raw development datasets are often rich, but they are not analysis-ready. In this video, I will show how to turn World Bank WDI data into a clean panel dataset that can be used for visualisation, regression and future research.

**What to show**

- A quick view of the raw WDI table
- A quick view of the final cleaned panel dataset
- A sentence on why this workflow matters for development and sustainability research

## Roadmap

**What to say**

We will follow five steps:

1. Introduce the WDI dataset.
2. Read and inspect the data with pandas.
3. Select countries and indicators.
4. Reshape the data into panel format.
5. Check missing values and export the cleaned file.

**What to show**

A simple slide or markdown cell with the five steps.

## Segment 1: Introduce the Dataset

**Teaching point**

The WDI dataset contains country-level indicators across many years. It is useful for economic, social, environmental and sustainability analysis, but the raw structure must be cleaned before analysis.

**What to say**

The World Development Indicators dataset includes many indicators for many countries and years. This makes it powerful, but also difficult for beginners. Before we can draw graphs or run regressions, we need to understand its structure and convert it into a cleaner format.

**What to show**

- Country columns
- Indicator columns
- Year columns
- Why wide-format year columns are inconvenient for later analysis

**Key terms**

- WDI
- indicator
- country-year observation
- wide format
- long format
- panel data

## Segment 2: Read and Inspect the Data

**Teaching point**

The first step in data analysis is not modelling. It is inspection.

**Suggested code**

```python
import pandas as pd

df = pd.read_csv("data/wdi/WDI_course_subset.csv")
df.head()
df.info()
df.columns
```

**What to say**

After reading the file, I first use `head()` to see the first few rows, `info()` to understand the number of rows and columns, and `columns` to check variable names. This gives us a quick diagnostic view before we make any changes.

**What to show**

- The first few rows of the dataset
- Output from `info()`
- A short explanation of column names and data types

## Segment 3: Select Countries and Indicators

**Teaching point**

Real datasets often contain more information than we need. Selecting a smaller subset makes the workflow easier to understand and reproduce.

**Suggested code**

Adjust the exact column names to match the notebook.

```python
selected_countries = ["China", "United States", "India"]

df_selected = df[
    df["Country Name"].isin(selected_countries)
]

df_selected.head()
```

If the notebook selects indicators:

```python
selected_indicators = [
    "GDP growth (annual %)",
    "Population, total",
    "CO2 emissions (metric tons per capita)"
]

df_selected = df_selected[
    df_selected["Indicator Name"].isin(selected_indicators)
]
```

**What to say**

Here I use a small set of countries and indicators as a teaching example. The same logic can be applied to any country group or indicator group. This is also how we turn a very large dataset into a focused research dataset.

**What to show**

- Filtering by country
- Filtering by indicator
- The resulting smaller table

## Segment 4: Reshape Wide Data into Panel Data

**Teaching point**

This is the core transformation. WDI data often stores years as columns, but many analysis tasks require a country-year panel format.

**Suggested code**

```python
df_long = df_selected.melt(
    id_vars=["Country Name", "Country Code", "Indicator Name"],
    var_name="Year",
    value_name="Value"
)

df_long.head()
```

If using a pivot table:

```python
panel = df_long.pivot_table(
    index=["Country Name", "Year"],
    columns="Indicator Name",
    values="Value"
).reset_index()

panel.head()
```

**What to say**

The `melt()` function turns year columns into rows. This gives us a long-format dataset. Then `pivot_table()` can place each indicator into its own column, so each row becomes one country-year observation. This is the format we usually want for visualisation, regression and indicator analysis.

**What to show**

- Before and after reshaping
- Why `Year` becomes a variable
- Why each country-year row is useful

## Segment 5: Check Missing Values and Export

**Teaching point**

Cleaning is not finished until we inspect missing values and save a reusable output.

**Suggested code**

```python
panel.isna().sum()

panel.to_csv("outputs/wdi_panel_clean.csv", index=False)
```

**What to say**

Missing values are common in development data. Before we use this dataset for graphs or regression, we need to know where the gaps are. Finally, I export the cleaned panel dataset so that later lessons can reuse the same output.

**What to show**

- Missing-value counts
- Exported CSV file
- A short note on reproducible workflow

## Closing Recap

**What to say**

In this lesson, we transformed raw WDI data into a clean panel dataset. We read and inspected the data, selected countries and indicators, reshaped wide-format data into panel format, checked missing values and exported the cleaned file. This workflow is useful for development research, sustainability indicators, policy analysis and classroom teaching.

The code, data subset and exercises are available in the GitHub repository linked below.

## Description for YouTube

```text
In this teaching demo, I show how to build a clean country-year panel dataset from World Bank World Development Indicators (WDI) data using Python and pandas.

Learning objective:
By the end of this video, viewers can read WDI data, inspect its structure, select countries and indicators, reshape wide-format data into panel format, check missing values and export a cleaned dataset.

Data/source:
World Bank World Development Indicators (teaching subset)

Tools:
Python, pandas, Jupyter Notebook

GitHub repository:
https://github.com/hanyu2010wendy/Big-Data-Analysis-2025

Portfolio relevance:
This video is part of an online teaching portfolio demonstrating data-based teaching, research data preparation, applied Python instruction and reproducible educational materials.

#Python #DataAnalysis #WDI #PanelData #Economics #DevelopmentData
```

## Portfolio Note

This video can be described in a CV or mini portfolio as:

> Designed and published an English-language Python teaching demo using World Bank WDI data, with GitHub-hosted notebooks, teaching datasets, assignments and reproducible outputs. The lesson demonstrates data cleaning, panel-data preparation, missing-value inspection and applied research workflow design.

## Recording Checklist

Before recording:

- Open the correct notebook.
- Confirm the dataset path works.
- Prepare one slide or markdown cell with the roadmap.
- Keep the GitHub repository open for the closing.
- Use large enough font size in Jupyter or Colab.
- Hide unnecessary browser tabs.
- Record a short test clip to check audio.

During recording:

- Explain the purpose before the syntax.
- Pause after important outputs.
- Do not over-explain every line of code.
- Keep returning to the main workflow: raw data to clean panel dataset.

After recording:

- Upload with the final title.
- Add the standard description and GitHub link.
- Put the video into the playlist: **Big Data Analysis with Python: Teaching Demo Portfolio**.

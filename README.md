# Big Data Analysis Course (English Edition)

This repository is a cleaned, reorganized, and English-translated version of the original Big Data Analysis teaching materials.

## What was changed

- Remaining Chinese notebooks were translated into English.
- Lecture materials and assignments were reorganized into separate folders.
- Missing assignment templates were added where needed.
- A lightweight WDI teaching subset was created so the repository is easier to host on GitHub.
- Platform-specific absolute paths were replaced with relative project paths that work after cloning the repository locally or in Colab.
- A short English variable dictionary and province-name mapping were added for the China-focused datasets.
- MacOS system files and notebook checkpoints were excluded from the cleaned package.

## Repository structure

- `lectures/`: lecture notebooks
- `assignments/`: homework notebooks
- `data/`: teaching datasets and helper files
- `assets/`: static images used in the notebooks
- `outputs/`: suggested folder for exported tables and figures

## Running the notebooks

Each notebook includes a small path helper that searches for the project root automatically.

### Local Jupyter
Clone the repository and open the notebooks inside the repository folder.

### Google Colab
Clone the repository first, then open the notebook from the cloned folder.  
The path helper assumes the `data/` and `assets/` folders are present in the same repository.

### Live data note
The finance notebooks use live market-data APIs. For fully reproducible offline teaching, keep exported outputs or prepare a local fallback dataset.

## Data notes

- `data/wdi/WDI_course_subset.csv` is a GitHub-friendly teaching subset, not the full WDI raw file.
- If you want to assign arbitrary countries for student homework, replace the subset with the full WDI data or use Git LFS / external storage.
- `data/china/china_panel_data_dictionary.csv` contains English aliases for the main China panel variables.
- `data/china/province_name_mapping.csv` maps Chinese province names to English names.

## Modules

### Lectures
1. WDI data analysis
2. Chinese data analysis
3. Data visualization with WDI
4. Multivariable linear regression
   - panel-data example
   - single-country example
5. Principal component analysis (PCA)
6. Financial data
   - AKShare (China-market version)
   - Yahoo Finance (international / institution-facing version)
7. Geographic mapping with China data

For international-facing teaching, start with `lectures/06_financial_data/Financial_data_with_Yahoo_Finance.ipynb`.

### Assignments
1. Homework 1: blank + solution
2. Homework 2: blank + solution
3. Homework 3: blank + solution
4. Homework 4: blank + solution
5. Homework 5: blank + solution
6. Homework 6: blank + solution (Yahoo Finance / international finance case)
7. Homework 7: blank only

## Missing items from the original package

See `COURSE_AUDIT.md` for a full review, including missing solution notebooks and missing source files referenced by the original materials.

## Video tutorials

Existing public videos: YuHan-19  
https://www.youtube.com/@YuHan-19

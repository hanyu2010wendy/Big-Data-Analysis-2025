# Course Audit and Review Notes

## Reorganization decisions

The cleaned repository uses two main top-level folders:
- `lectures/`
- `assignments/`

This matches the teaching logic more clearly than the original mixed structure.

## Original materials and cleaned destinations

| Original item | Cleaned destination | Type | Status |
|---|---|---|---|
| `01 WDI data analysis/WDI data analysis.ipynb` | `lectures/01_wdi_data_analysis/WDI_data_analysis.ipynb` | lecture | cleaned |
| `01 WDI data analysis/Homework1.ipynb` | `assignments/01_wdi_data_analysis/Homework1_solution.ipynb` | homework solution | translated |
| *(missing blank notebook)* | `assignments/01_wdi_data_analysis/Homework1_blank.ipynb` | homework template | created |
| `02 Chinese data analysis/lecture/Chinese data_English.ipynb` | `lectures/02_chinese_data_analysis/Chinese_data_analysis.ipynb` | lecture | cleaned |
| `02 Chinese data analysis/homework/Homework2_answer.ipynb` | `assignments/02_chinese_data_analysis/Homework2_solution.ipynb` | homework solution | cleaned |
| `02 Chinese data analysis/homework/练习2_Homework2.ipynb` | `assignments/02_chinese_data_analysis/Homework2_blank.ipynb` | homework template | expanded |
| `03 Data visualization/Data visualization_WDI_English.ipynb` | `lectures/03_data_visualization/Data_visualization_with_WDI.ipynb` | lecture | cleaned |
| `03 Data visualization/Homework3_English.ipynb` | `assignments/03_data_visualization/Homework3_solution.ipynb` | homework solution | cleaned |
| *(missing blank notebook)* | `assignments/03_data_visualization/Homework3_blank.ipynb` | homework template | created |
| `04 .../Lecture/Regression_English.ipynb` | `lectures/04_multivariable_linear_regression/Regression_panel_data_example.ipynb` | lecture | cleaned |
| `04 .../Lecture/多元回归.ipynb` | `lectures/04_multivariable_linear_regression/Regression_single_country_example.ipynb` | lecture | translated |
| `04 .../Homework/Homework4.ipynb` | `assignments/04_multivariable_linear_regression/Homework4_solution.ipynb` | homework solution | translated |
| *(missing blank notebook)* | `assignments/04_multivariable_linear_regression/Homework4_blank.ipynb` | homework template | created |
| `05 .../PCA_English.ipynb` | `lectures/05_principal_component_analysis/PCA_with_HDI_and_WDI.ipynb` | lecture | cleaned |
| `05 .../Homework5_English.ipynb` | `assignments/05_principal_component_analysis/Homework5_blank.ipynb` | homework template | cleaned |
| `06 Financial data/Financial data_English.ipynb` | `lectures/06_financial_data/Financial_data_with_AKShare.ipynb` | lecture | cleaned and corrected |
| `07 Geographic map/地理分布图课件.ipynb` | `lectures/07_geographic_mapping/Geographic_mapping_with_China_data.ipynb` | lecture | translated |
| `07 Geographic map/课程实践周作业.ipynb` | `assignments/07_geographic_mapping/Homework7_blank.ipynb` | homework template | translated |

## Missing answers that still require your decision

1. **Homework 5 (PCA report assignment)**  
   No solution notebook was included in the uploaded package.

2. **Homework 7 (geographic mapping / practice-week assignment)**  
   No solution notebook was included in the uploaded package.

## Missing source files referenced by the original materials

1. **`国家名称与学号.csv`**  
   Referenced in the original PCA assignment, but not included in the uploaded package.  
   I added `data/wdi/country_assignment_template.csv` as a placeholder template.

2. **`portfolio.jpg` / `投资组合.jpg`**  
   Referenced in the financial-data notebook, but not included in the uploaded package.  
   The cleaned notebook replaces the broken image reference with explanatory text.

## Technical issues fixed during cleanup

1. **GitHub file-size problem for WDI raw data**  
   The original raw WDI CSV files were too large for a standard GitHub repository.  
   I created `data/wdi/WDI_course_subset.csv` so the cleaned repository is easier to host.

2. **Absolute platform-specific paths**  
   The original notebooks used Baidu AI Studio or local OneDrive paths.  
   These were replaced with repository-relative paths.

3. **macOS system files**  
   `.DS_Store`, `__MACOSX`, and notebook checkpoint clutter were excluded from the cleaned package.

4. **Finance notebook syntax error**  
   The original efficient-frontier section contained a stray `for tar in target_returns.` line.  
   The cleaned notebook fixes this.

5. **Repeated font dependency**  
   Several notebooks depended on `SimHei.ttf` and platform-specific Chinese font configuration.  
   The cleaned notebooks reduce or remove that dependency where possible.

## Content notes you may want to review before publishing

1. **Financial-data module is China-market specific**  
   This is fine if you want to showcase regional expertise.  
   If you are targeting international organizations, you may later want to add one more finance notebook based on a more globally familiar data source.

2. **PCA index sign convention**  
   The PCA notebook keeps the original negative sign in the composite index calculation.  
   Because PCA signs are arbitrary, you may want to add one sentence explaining why you keep or reverse the sign.

3. **Assignment coverage is uneven**  
   Modules 1–4 now have both blank and solution notebooks.  
   Modules 5 and 7 still need your decision on how much solution guidance you want to publish.

4. **WDI subset vs. full data**  
   The cleaned repository uses a teaching subset for GitHub convenience.  
   If you want fully open-ended student assignments, decide later whether to host the full WDI file elsewhere or require students to download it themselves.

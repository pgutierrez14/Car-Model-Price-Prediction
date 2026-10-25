# Changes relative to the original notebook

This revision keeps **every one of the 20 original cells in the same order**, including the exploratory figures and the author's choice of model, manual mappings, train/test ratio, and visualization workflow. The untouched source is at `original/cars_original.ipynb`.

## Edits within original cells

- **Cell 1 (imports):** Reformatted a multi-line metrics import only.
- **Cell 3 (data load):** Kept Kaggle source and printed paths, replaced a personal Windows file path with a portable relative dataset path and local-file fallback.
- **Cell 4 (data exploration):** Avoided `print(df.info())` displaying `None`.
- **Cell 5 (cleaning):** Included nullable Pandas string columns when inspecting text; checked label mapping; corrected `alfa-romero` to `alfa-romeo` in addition to the original author's spelling fixes.
- **Cell 7 (numeric EDA):** Kept all original plots; corrected comment that falsely claimed the model already used log(price); hid unused subplot and set plot colors explicitly for compatibility.
- **Cell 8 (categorical EDA):** Kept original boxplots; included nullable string dtype during text selection; hid unused subplot.
- **Cell 10 (redundancy checks):** Made both original cross-tabs visible and completed the previously commented-out comparison of compression ratios.
- **Cell 11 (feature choices):** Clarified that `fuelsystem` is not fully duplicated by `fueltype`.
- **Cell 13 (split):** Kept the same 70/30 split and seed; checked unseen categories directly in test vs. train.
- **Cell 15 (brand tiers):** Kept original `price_tier` thresholds and `Medium` fallback, but estimated the brand medians using the training set only to prevent target leakage.
- **Cell 16 (dummy encoding):** Kept mode reference categories and `pd.get_dummies`; created train dummy schema first and aligned test to it to avoid test-set feature learning.
- **Cell 18 (scaling/model):** Kept original `MinMaxScaler`, linear regression, plots and metrics; added `.copy()` to avoid slice-assignment problems.
- **Cell 19 (comparison plots):** Retained as written.

## Added after original analysis

- A markdown introduction to additional model checks.
- A residual analysis and a test-set comparison against the train-mean baseline.
- A concluding markdown cell with interpretation prompts and limitations.

## Output preservation / verification

- Original exploratory chart outputs have been preserved (some old chart labels may differ slightly until a fresh run).
- The data-loading output was cleared to avoid exposing a personal Windows filesystem path.
- Previous model outputs in cells 15, 16, 18, and 19 were cleared **only** because they relate to the original leakage-affected model and would no longer reflect the corrected code.
- No new model metrics are claimed; execute the revised notebook with the actual CSV to get trustworthy figures.
- The corrected notebook is valid notebook JSON. CSV-dependent results could not be re-executed here because the original dataset file is not among the uploaded artifacts.

# repo: uber-trip-analysis

**Short description**

End-to-end Uber trip demand analysis and forecasting pipeline (Python, Colab, Power BI). Includes data cleaning, hourly aggregation, feature engineering, Random Forest demand model, evaluation, visuals, and Power BI-ready exports.

---

## Files in this repo

* `notebooks/uber_trip_analysis.ipynb` — Colab-ready notebook (full pipeline).
* `data/Uber_Clean_Dataset.csv` — cleaned trip-level CSV (generated).
* `data/Uber_Feature_Engineered.csv` — hourly aggregated + engineered features.
* `model/uber_hourly_rf_joblib.pkl` — trained RandomForest model (joblib).
* `assets/` — dashboard PNGs and images.
  
> **Note (Colab paths)**: If you ran the preprocessing & notebook in Google Colab, the original file path used was: `/content/Uber-Jan-Feb-FOIL.csv`. The generated notebook and model are saved under `/mnt/data/` in this environment (e.g. `/mnt/data/uber_trip_analysis.ipynb`, `/mnt/data/uber_hourly_rf_joblib.pkl`). When you upload files to your GitHub repo, place the CSV(s) under the `data/` folder.

---

## Project overview

This project analyzes Uber FOIL trip records (Jan–Feb) to understand demand patterns and build a basic hourly-demand predictive model. The pipeline covers:

1. Data loading and parsing
2. Hourly aggregation of trips
3. Exploratory Data Analysis (time series, daily totals)
4. Feature engineering (hour, dayofweek, lag features)
5. Time-based train/test split
6. Model training (RandomForestRegressor)
7. Evaluation and visualization
8. Export Power BI–ready CSVs and PNGs

---

## Quick start (Colab)

1. Open Google Colab and upload the dataset to `/content/Uber-Jan-Feb-FOIL.csv` or connect to your Google Drive and update `DATA_PATH` accordingly.
2. Upload or open `notebooks/uber_trip_analysis.ipynb` in Colab.
3. Run cells from top → bottom. The notebook will:

   * Create `data/Uber_Clean_Dataset.csv` and `data/Uber_Feature_Engineered.csv`.
   * Save trained model to `/content/uber_hourly_rf_joblib.pkl` or `/mnt/data/uber_hourly_rf_joblib.pkl`.
   * Export PNG charts to `/mnt/data/`.

---

## How to run locally (short)

1. Clone this repo.
2. Create a Python venv and install dependencies (pandas, scikit-learn, matplotlib, joblib).
3. Place `Uber-Jan-Feb-FOIL.csv` in `data/` and update `DATA_PATH` in the notebook or script.
4. Run the notebook or the provided script to generate outputs.

Example dependencies (requirements.txt):

```
pandas
numpy
matplotlib
scikit-learn
joblib
jupyterlab
openpyxl
```

---


## Results & outputs

* Sample charts: `assets/chart_hourly_timeseries.png`, `assets/chart_actual_vs_predicted.png`, `assets/chart_combined.png`.
* Notebook generated: `notebooks/uber_trip_analysis.ipynb` (Colab-ready).
* Model file: `model/uber_hourly_rf_joblib.pkl`.

---

## Next steps (ideas)

* Replace RandomForest with LightGBM/XGBoost and add hyperparameter tuning.
* Add external features (weather, events, holidays).
* Build zone-based models (k-means clustering on lat/lon).
* Create a Power BI `.pbix` manually using the exported CSV.

---

## License

MIT License — feel free to reuse and adapt for learning/projects.

---

*Generated README: replace local Colab paths with repo-relative paths when you commit.*

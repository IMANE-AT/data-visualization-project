# Vegetation Dynamics in Morocco (2018–2025)

Satellite NDVI analysis of vegetation in Morocco from 2018 to 2025, comparing the Souss-Massa and Haouz plains and avocado plots in the Souss plain with interactive Plotly charts.

I used 93 monthly observations from January 2018 to September 2025 to compare seasonal vegetation patterns across two agricultural plains and between avocado plots and the rest of the Souss plain. The analysis uses the Normalized Difference Vegetation Index (NDVI), a satellite-derived indicator of vegetation greenness.

## Analysis

| Question | Visualization |
| --- | --- |
| How does vegetation greenness vary across seasons in the Souss-Massa and Haouz plains? | Monthly NDVI line chart and grouped bars comparing June–August averages by year |
| How do avocado plots compare with the rest of the Souss plain? | Monthly line chart, box plots, and month-by-year heatmaps |

I prepared two CSV exports from Google Earth Engine with pandas, reshaped the monthly series for comparison, and built six interactive charts with Plotly.

## Findings

- Mean summer NDVI was higher in the Haouz than in the Souss in each year. Between 2018 and 2025, it fell from **0.178 to 0.134** in the Haouz and from **0.107 to 0.088** in the Souss, with fluctuations in both series.
- The avocado-plot series had a higher NDVI than the rest-of-Souss series in all **93 months**. The median monthly NDVI was **0.340** for avocado plots and **0.103** for the rest of the plain.

NDVI measures vegetation greenness. Attributing these differences to drought or irrigation would require additional evidence, such as rainfall, irrigation, or water-use records.

## Run the notebook

From the repository root, install the dependencies and start Jupyter.

```bash
python -m pip install -r requirements.txt
jupyter notebook DATA_VIZ_IMANE_ATIF_DS.ipynb
```

To rerun all cells, place the following Google Earth Engine CSV exports next to the notebook. Each file should have a header row followed by monthly observations, with dates in `Jan 1, 2018` format.

| CSV export | Expected column order |
| --- | --- |
| `NDVI_Souss_vs_Haouz_2018-2025.csv` | Date, Souss NDVI, Haouz NDVI |
| `NDVI_Avocat_vs_Souss_2018-2025.csv` | Date, avocado-plot NDVI, rest-of-Souss NDVI |

The CSV exports are kept outside version control. The [original notebook](DATA_VIZ_IMANE_ATIF_DS.ipynb) includes the saved analysis and chart outputs.

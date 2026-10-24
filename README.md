# Big Data Customer Intelligence and Recommendation System Using Apache Spark

A big data analytics project built with Python, PySpark, and Apache Spark to explore e-commerce transactions, analyse sales patterns, segment customers, estimate customer spending, and identify products purchased together.

## Overview

E-commerce platforms produce data about customers, orders, products, payments, sellers, and reviews. This project uses the Brazilian E-Commerce Public Dataset by Olist to demonstrate how related CSV files can be processed and analysed through a Spark-based workflow.

The implementation was developed in Google Colab using Spark in local mode. It combines data preparation, Spark SQL queries, machine learning, product co-purchase analysis, visualisation, and a small Spark-versus-Pandas timing comparison.

## Features

- Load multiple Olist CSV files into PySpark DataFrames.
- Remove duplicate rows and filter records with missing key identifiers.
- Join customer, order, order-item, and product information.
- Analyse monthly sales, order counts, average item prices, and product-category revenue.
- Segment customers into four groups with K-Means.
- Estimate customer spending with Linear Regression and evaluate it using RMSE, MAE, and R².
- Identify product pairs that occur in the same order.
- Visualise customer-cluster distribution and monthly sales trends.
- Compare execution times for a selected aggregation in Spark and Pandas.
- Export analysis outputs as CSV files.

## Dataset

**Name:** Brazilian E-Commerce Public Dataset by Olist  
**Source:** Kaggle  
**Link:** https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

The dataset contains separate CSV files for customers, orders, order items, products, payments, reviews, sellers, geolocation, and product-category translations.

Download the dataset from Kaggle and place the extracted CSV files in one folder. The notebook used for this project expects the files to be available under `/content/olist_data` in Google Colab.

## Technologies Used

- Python
- Apache Spark
- PySpark DataFrames and Spark SQL
- Spark MLlib
- K-Means clustering
- Linear Regression
- Pandas
- Matplotlib
- Google Colab

## Project Workflow

1. Set up the Google Colab environment and install PySpark.
2. Upload and extract the dataset ZIP file.
3. Load the CSV files into Spark DataFrames.
4. Inspect schemas, row counts, and sample records.
5. Clean duplicate records and filter missing key identifiers.
6. Join related order, customer, item, and product data.
7. Calculate sales and product-category summaries.
8. Build customer-level features and apply K-Means clustering.
9. Train and evaluate a Linear Regression model.
10. Find product pairs that occur together in the same order.
11. Plot monthly sales and customer-cluster distribution.
12. Compare selected Spark and Pandas aggregation timings.
13. Export the resulting tables to CSV files.

## Run the Project

### Option 1: Google Colab

1. Open [Google Colab](https://colab.research.google.com/).
2. Upload the project notebook (`.ipynb`) to Colab.
3. Download the dataset ZIP from Kaggle and upload it when prompted by the notebook.
4. Run the notebook cells in order, starting with the installation and setup cells.
5. Review the generated tables, evaluation metrics, graphs, and saved CSV outputs.

### Option 2: PySpark environment

Install the required packages:

```bash
pip install pyspark pandas matplotlib
```

Make sure the dataset files are available in the path configured by the notebook. Then run the notebook in an environment with Java and Apache Spark-compatible PySpark installed.

## Output Files

The notebook exports the following analysis results to `/content/project_outputs`:

- `monthly_sales.csv` — monthly sales summary
- `customer_clusters.csv` — customer-cluster summary
- `spending_predictions.csv` — actual and predicted spending values
- `product_recommendations.csv` — frequently co-purchased product pairs

The notebook also displays a monthly sales trend chart and a customer-cluster distribution chart.

## Important Notes and Limitations

- Spark runs in **local mode** in the Google Colab implementation; this is not a multi-node cluster deployment.
- The Spark-versus-Pandas timing comparison applies only to the selected operation and runtime environment. Spark may not be faster for a small workload.
- The product analysis identifies products appearing in the same order. It is a basic co-purchase analysis, not a fully personalised recommendation engine.
- The Linear Regression model is exploratory. Its features are derived from the same customer-level data as the spending target, so the results should not be interpreted as proof of future-spending prediction capability.
- Actual performance and model-quality claims should be based on the outputs from the executed notebook.

## Repository Structure

A suggested repository structure is:

```text
.
├── README.md
├── INT315_Cluster_Computing_Project.ipynb
├── screenshots/
└── project_outputs/
    ├── monthly_sales.csv
    ├── customer_clusters.csv
    ├── spending_predictions.csv
    └── product_recommendations.csv
```

The output files and screenshots are generated by running the notebook; add them to the repository only if you intend to publish them.

## Academic Context

**Course:** INT315 — Cluster Computing  
**Project:** Big Data Customer Intelligence and Recommendation System Using Apache Spark

## Acknowledgements

Thanks to Olist for providing the public e-commerce dataset and to Kaggle for hosting it.

## License

The dataset is distributed under the license stated on its Kaggle page. Check that license before redistributing the dataset files. This repository's code and documentation do not automatically change the dataset's license.

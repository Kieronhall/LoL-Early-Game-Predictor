# LoL-Predictive-Pipeline: OOP Analysis & Automated Reporting

## 📌 Overview
This repository features a production-ready machine learning pipeline designed to analyze early-game telemetry from High-Diamond *League of Legends* matches. The project investigates the "snowball effect"—quantifying how early-game advantages (gold, objectives, and map pressure) translate into match victories.

Refactored from a research-focused implementation into a modular, **Object-Oriented (OOP)** framework, this version prioritizes code reusability, clear separation of concerns, and automated professional reporting.

## 🚀 Key Features
* **Modular OOP Design**: The logic is encapsulated into specialized classes (`DataHandler`, `ClusterAnalyzer`, `ModelTrainer`), making the pipeline easy to scale or adapt to other datasets.
* **Automated PDF Reporting**: Features a custom `ReportGenerator` class that dynamically compiles all statistical analysis, benchmarking graphs, and UMAP visualizations into a final professional PDF.
* **Unsupervised Pattern Discovery**: Uses **UMAP** for dimensionality reduction and **K-Means** to identify latent game states (e.g., "Extreme Objective Dominance" vs. "High-Variance Scraps").
* **Multi-Model Benchmarking**: Automatically compares 5 classifiers (Logistic Regression, Random Forest, SVM, Gradient Boosting, Naïve Bayes) across three different data configurations:
    * **Raw Features**: Basic 10-minute telemetry.
    * **Cluster Features**: High-level match archetypes.
    * **Combined**: A hybrid approach for maximum predictive power.

## 🛠️ Pipeline Architecture
1.  **`LoLDataHandler`**: Ingests data and performs initial EDA and feature distribution analysis.
2.  **`LoLDataCleaner`**: Implements feature engineering (e.g., `killsRatio`) and removes "data leakage" by isolating independent team variables.
3.  **`DimensionalityReducer`**: Projects high-dimensional game data into 2D space for visualization.
4.  **`ClusterAnalyzer`**: Partitions matches into 5 distinct game archetypes to study win-rate variance.
5.  **`ModelTrainer` / `ExperimentRunner`**: Orchestrates supervised learning experiments and regression analysis.
6.  **`ReportGenerator`**: The final output stage that exports the technical summary to `LoL_Analysis_Report.pdf`.

## 📈 Results Highlights
* **Accuracy**: Predicts the winner with **~73% accuracy** within the first 10 minutes of play.
* **Determinism**: Early-game performance explains **95.4% of the variance** ($R^2 = 0.9544$) in gold accumulation, suggesting a highly deterministic meta.
* **Dominance States**: The pipeline identifies that only **~13% of matches** are truly "neutral" at the 10-minute mark; the rest are already leaning toward a clear winner.

## 💻 Installation & Usage
1.  **Clone the Repo**:
    ```bash
    git clone [https://github.com/yourusername/LoL-Predictive-Pipeline.git](https://github.com/yourusername/LoL-Predictive-Pipeline.git)
    ```
2.  **Install Requirements**:
    ```bash
    pip install pandas numpy scikit-learn matplotlib seaborn umap-learn
    ```
3.  **Run the Notebook**:
    Execute `portfolio_submission.ipynb`. 
4.  **Check Output**:
    The pipeline will generate `LoL_Analysis_Report.pdf` in the root directory upon completion.

## 👤 Author
**Kieron Hall**
*Data Science Portfolio Project*

# IMDb Review Sentiment by Genre — DS4002 Project 1

This repository contains all code, documentation, and outputs for **DS4002 Project 1**. The project merges the **ACL IMDb Movie Reviews Dataset** with the **IMDb Title Basics Dataset** to create a combined dataset of reviews linked with official IMDb titles and genres. Using this dataset, we perform baseline sentiment analysis and evaluate results by genre.
## Goal
This file serves as an orientation to everyone who comes to the repository.  
It enables users to get their bearings and reproduce results.

## Contents of the Repository

- **DATA**
  - `Appendix.pdf`: Contains dataset descriptions, variable dictionaries, and descriptive statistics.
  - `README.md`: Instructions for downloading and preparing the raw datasets.
- **SCRIPTS**
  - `project1.ipynb`: Jupyter/Colab notebook with the full dataset creation and analysis pipeline.
- **OUTPUT**
  - `OUTPUT_Project1.pdf`: Final report including figures, tables, and summary of findings.
- **LICENSE.md**: MIT License for code and documentation in this repository.
- **README.md**: (this file) Orientation, environment requirements, and reproduction instructions.


## Section 1: Software and Platform

**Software Used**
- Python 3.10+  
- Jupyter Notebook / Google Colab  

**Required Packages**
- `pandas`  
- `numpy`  
- `scikit-learn`  
- `matplotlib`  
- `tqdm`  

## Section 2: Map of Documentation
```
Project1
├── DATA
│   ├── Appendix.pdf            # Data dictionary and descriptive statistics
│   └── README.md               # How to obtain the raw datasets
├── OUTPUT
│   └── OUTPUT_Project1.pdf     # Final report with results
├── SCRIPTS
│   └── project1.ipynb          # Full dataset creation + analysis pipeline
├── LICENSE.md                  # MIT License for repository code
└── README.md                   # Main orientation file (this document)
```
## Section 3: Instructions for Reproducing Results

Follow these steps to reproduce the analysis from scratch.

### Step 1: Download Raw Data
1. Download the **ACL IMDb Movie Reviews** dataset (Large Movie Review Dataset v1.0) from:  
   [https://ai.stanford.edu/~amaas/data/sentiment/](https://ai.stanford.edu/~amaas/data/sentiment/)  
2. Download the **IMDb Title Basics** dataset (`title.basics.tsv.gz`) from:  
   [https://datasets.imdbws.com/](https://datasets.imdbws.com/)  
3. Extract the `title.basics.tsv` file from the compressed `.gz` file.  
   - *Do not unzip the reviews archive; the pipeline handles this automatically.*  

### Step 2: Upload to Environment
- **If using Google Colab**  
  - Upload both datasets (`aclImdb_v1.tar.gz` and `title.basics.tsv`) to your Colab content folder (`/content/`).  
- **If running locally**  
  - Place the datasets in the same folder as the notebook or update the path variables accordingly.  
### Step 3: Configure File Paths
In `SCRIPTS/project1.ipynb`, confirm that the paths in the configuration cell match your environment. For example:
```python
ACL_ARCHIVE_TGZ = Path("/content/aclImdb_v1.tar.gz")
TITLE_BASICS_PATH = Path("/content/title.basics.tsv")
ACL_ROOT_DIR = Path("/content/aclImdb")
OUTPUT_PARQUET = Path("/content/imdb_sentiment_with_genres.parquet")
OUTPUT_CSV = Path("/content/imdb_sentiment_with_genres.csv")
WRITE_CSV_TOO = False
```

### Step 4: Run the Notebook
1. Open `project1.ipynb` in Colab or Jupyter.  
2. Run all cells in order. The pipeline will:  
   - Extract and process the ACL IMDb reviews  
   - Merge reviews with the IMDb Title Basics dataset  
   - Normalize genres and expand multi-genre entries  
   - Perform baseline sentiment analysis  
   - Generate plots and tables summarizing results  
   - Save the merged dataset to `OUTPUT_PARQUET` (and optionally `.csv`)  

### Step 5: Export Results
- The notebook exports a PDF report summarizing the findings.  
- Save or move the exported PDF to `OUTPUT/OUTPUT_Project1.pdf` to match the repository structure.  

### Step 6: Verify Output
- **Merged dataset size:** ~114,137 rows, ~5,000 unique movies  
- **Review distribution:** 25k positive, 25k negative (from ACL dataset)  
- **Notebook output:** Plots of sentiment distribution by genre and baseline model performance metrics  

### Troubleshooting
- **File not found errors** → Double-check dataset paths.  
- **Package issues** → Run `pip install` commands and restart runtime if necessary.  
- **Upload timeouts in Colab** → Use the “Files” panel or mount Google Drive.  

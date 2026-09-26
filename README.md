SWYNEX Task 1: Data Cleaning & Preparation
Dataset
Netflix Movies and TV Shows dataset from Kaggle.Started with 8,807 rows and 12 columns.

Tools Used
Python (pandas, numpy) in Google Colab.

Problems I Found
Missing values: director 2,634 · cast 825 · country 831 ·date_added 10 · rating 4 · duration 3 (total 4,307)
date_added was stored as text (object) instead of proper dates
3 rows had duration values (e.g., "74 min") wrongly placedinside the rating column
Duplicate check: 0 duplicates found
Cleaning Steps & Why
Checked and removed duplicates — prevents double-counting
Converted date_added from text to datetime — enablessorting and filtering by date
Fixed misplaced values — moved "74 min" etc. from ratingto the correct duration column
Filled missing director/cast/country with "Unknown" —deleting them would lose ~30% of the data
Filled missing rating with "Not Rated" — a standard industry label
Removed the 10 rows with no date_added — minimal loss;a show without a date cannot be analyzed by date
Results
Before	After
Rows	8,807	8,797
Missing values	4,307	0
date_added type	text	datetime64
Before cleaning
before

After cleaning
after

Files
netflix_cleaned.csv — the cleaned dataset
SWYNEX_Task1.ipynb — full Python code, step by step
before.png / after.png — proof screenshots

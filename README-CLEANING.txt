vgsales.csv

PUBLIC DATASET
Dowloaded from: https://www.kaggle.com/datasets/gregorut/videogamesales?select=vgsales.csv

==============================

Skills:

Excel
Filters
CSV file

==============================

EXCEL CSV FILE INFO

Rows: 16598 (not including header row)
Columns: 11

==============================

FILE CLEANING

By inspecting the csv Excel file, some cleaning has to be done. There are:
-Rows with missing Year ('it says N/A')
-Rows with missing Publisher ('it says N/A' or 'Unknown')
-Rows where Global sales doesn't equal to the sum of regional sales (NA sales, 
EU sales, JP sales, Other sales)

The missing fields can be analyzed by simply putting a filter on the 1st row of the 
Excel file (the categories row) and looking at every column for categories like N/A 
or Unknown.
The Global sales can be reviewed by suming the regional sales in another column and
comparing that value with Global sales.

==============================

MISSING FIELDS

Rows with missing values won't be deleted so as to conserve the most data possible and
because deleting rows will affect the global calculations, for example, total sales
globally.
The missing values will be replaced by ~Unknown ('Tilde' follows by 'Unknown').
The ~ character is the last character in alphabetical order in Python. So when sorting
data alphabetically these unknown categories will be shown last of all.

==============================

MAKING SURE 'UNKNOWN' IS NOT PART OF NAME

To make sure 'Unknown' is not part of a game name, we can go to the Excel file,
go to Search 'Unknown', and choose by columns, putting the cursor on the 1st cell.
The search will jump to the cell 'XCOM: Enemy Unknown' in the Name column, meaning
Unknown is part of the name. And that game is repeated several times.
As we have to avoid affecting that game name we cut that Name column into another sheet
and after doing the replacements, we paste back the cut Name column. Values will be 
unaffected.

==============================

CLEANING ORDER

1.Replaced Unknown by ~Unknown (203 fields replaced)
2.Replaced N/A by ~Unknown (329 fields replaced)
3.Deleted all commas (they affect the number of fields per row) (158 fields replaced)

==============================

GLOBAL SALES REVIEW

Note: All sales are in millions of dolars.

2 additional columns were created in the Excel file: Global Sales Sum, and Global
Sales Difference.

-Global Sales Sum: sum of NA sales, EU sales, JP sales, Other sales
-Global Sales Difference: difference between Global Sales Sum and Global Sales

1. +/- 20000$ difference: 10 games found
2. +/- 10000$ difference: 4501 games found

Difference sum total (absolute): 45,210,000$
Difference sum total: 4,590,000$

==============================

CLEAN CSV FILE

Copied the columns of the Excel file on which I worked into a new Excel file. Only the 11
columns with the clean data and fixed global sum. The first row with the headers wasn't copied.
Double checked that the sum of regional sales gave the Global sales (difference should be 0).

Save as: .csv (comma separated values)
Select 'no' in the conserve format window.

Clean file: vgsales-clean.csv
This project is a Business Intelligence pipeline built with Python in a Google Colab environment. It performs data cleaning, transformation, and dimensional modeling to create a structured data warehouse with facts and dimensions extracted from inventory, sales, and purchase data.

**Files Expected**
BegInvFINAL12312016.csv – Beginning inventory data
EndInvFINAL12312016.csv – Ending inventory data
PurchasesFINAL12312016.csv – Purchases data
sales.json – Sales data in JSON or JSON Lines format

**Features**
Cleans and standardizes inventory and sales datasets
Replaces missing numeric values with column averages
Converts sizes (e.g., "750ml" to "0.75L")
Parses and standardizes date formats (dd-mm-yyyy)
Removes duplicate records
Handles both CSV and JSON files (with optional JSON Lines parsing)
Builds star schema data warehouse:
Dimensions: DateDim, ProductDim, StoreDim, VendorDim
Fact tables: FactSales, FactInventory
Calculates business metrics:
StockReceived, StockSold, StockTurnover

**How It Works**
*Upload Raw Files*
Use the file upload dialogs to import your CSVs and JSONs or ZIP files containing them.
*Data Cleaning*
Missing values filled
Duplicate rows removed
Dates and size formats standardized
Data Transformation
Extracts dimension tables: product, store, vendor, date
Computes surrogate keys
Creates fact tables with merged data
*Output Generation*
Saves the following CSVs locally for download:
ProductDim.csv
StoreDim.csv
DateDim.csv
VendorDim.csv
FactSales.csv
FactInventory.csv

**Calculations**
StockTurnover = StockSold / onHandEnd
(Handled to avoid divide-by-zero errors)

**Output**
All CSVs are available for download after the transformation. The data can be used for downstream reporting or loading into BI tools like Power BI or Tableau. I have used in a further step Google Locker.

**Requirements**
Google Colab
Python 3.x
Libraries:
pandas
numpy
re
json
zipfile
os

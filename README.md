# Extracting Data from URL Example

This Python script processes a CSV file containing data about medical institutions, counts the number of institutions in each city, and displays the top five cities with the highest counts.

## Sample Code

```python

import pandas as pd
import numpy as np

# Load the data from the CSV file
url = "https://raw.githubusercontent.com/kiang/pharmacies/master/data.csv"
df = pd.read_csv(url)

# Counting the number of occurrences of each city (縣市)
city_count = df["縣市"].value_counts()

# Getting the top five cities with the highest number of occurrences
top_five = city_count.head(5)

# Printing the results
print(f"醫事機構數量前五高的縣市：{top_five}")
     

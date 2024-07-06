# Extracting Data from URL Example

This Python script processes a CSV file containing data about medical institutions, counts the number of institutions in each city, and displays the top five cities with the highest counts.

## Sample Code

```python
import pandas as pd

# Load the data from the CSV file
url = 'https://raw.githubusercontent.com/kiang/pharmacies/master/data.csv'
data = pd.read_csv(url)

# Extract the city name from the address (assuming the address starts with the city name)
data['city'] = data['地址'].apply(lambda x: x.split()[0] if pd.notnull(x) else 'Unknown')

# Count the number of medical institutions in each city
city_counts = data['city'].value_counts()

# Get the top 5 cities with the highest number of medical institutions
top_5_cities = city_counts.head(5)

# Display the result
print(top_5_cities)

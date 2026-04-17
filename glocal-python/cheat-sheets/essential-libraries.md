# Master Cheat Sheet: Essential Third-Party Libraries

This cheat sheet covers the most powerful and widely-used Python external libraries. It has a special focus on Data Manipulation (`pandas`) while also diving into HTTP Requests, Web Scraping, Math, and Visualization. 

## 1. Pandas (Data Manipulation & Analysis)
Pandas is the absolute gold standard for tabular data in Python.

### Import and basic initialization
```python
import pandas as pd

# Creating a DataFrame from a Dictionary
data = {
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35],
    'City': ['NY', 'LA', 'Chicago']
}
df = pd.DataFrame(data)

# Reading / Writing Files
df = pd.read_csv('data.csv')
df = pd.read_excel('data.xlsx', sheet_name='Sheet1')
df = pd.read_json('data.json')
# export back
df.to_csv('output.csv', index=False)
```

### Viewing and Inspecting Data
```python
df.head()          # View first 5 rows
df.tail(3)         # View last 3 rows
df.info()          # Summary of columns, non-null counts, types
df.describe()      # Summary statistics for numeric columns
df.shape           # (rows, columns) tuple
df.columns         # List of column names
df.dtypes          # Data types of each column
```

### Selecting & Filtering
```python
# Selecting Columns
df['Name']                  # Returns a Series
df[['Name', 'Age']]         # Returns a DataFrame

# Selecting Rows by Index (iloc) or Label (loc)
df.iloc[0]                  # First row
df.loc[df['Age'] > 30]      # Filter rows where Age > 30
df[(df['Age'] > 20) & (df['City'] == 'NY')] # Multiple conditions

# Handling Missing Data
df.dropna()                 # Drop rows with NaN values
df.fillna(0)                # Replace NaN values with 0
df['Age'].fillna(df['Age'].mean(), inplace=True) 
```

### Transformations & Operations
```python
# Create new column
df['Age In 10 Years'] = df['Age'] + 10

# Rename Columns
df.rename(columns={'Name': 'Full Name'}, inplace=True)

# Apply functions to elements
df['Full Name'] = df['Full Name'].apply(lambda x: x.upper())

# Sorting
df.sort_values(by='Age', ascending=False, inplace=True)

# Grouping & Aggregating
df.groupby('City')['Age'].mean() # Average age by city
df.groupby('City').agg({'Age': ['mean', 'min', 'max']})
```

---

## 2. NumPy (High-Performance Math & Arrays)
The foundational library for numerical computing.

```python
import numpy as np

# Creating Arrays
arr = np.array([1, 2, 3])
zeros = np.zeros((3, 3))       # 3x3 array of zeros
ones = np.ones((2, 2))         # 2x2 array of ones
range_arr = np.arange(0, 10, 2) # [0, 2, 4, 6, 8]
linspace = np.linspace(0, 1, 5) # 5 values from 0 to 1 evenly spaced

# Matrix Operations
arr_a = np.array([1, 2])
arr_b = np.array([3, 4])
arr_a + arr_b                  # [4, 6] (Element-wise addition)
arr_a * 10                     # [10, 20] (Scalar multiplication)
np.dot(arr_a, arr_b)           # 11 (Dot product)

# Useful functions
np.mean(arr)
np.median(arr)
np.std(arr)                    # Standard deviation
arr.reshape(3, 1)              # Change dimensions
```

---

## 3. Requests (HTTP & APIs)
The most human-friendly way to make web requests and consume APIs.

```python
import requests

# Making a GET request
response = requests.get('https://api.github.com')

# Inspecting the response
response.status_code       # 200 (OK), 404 (Not Found), etc.
response.text              # Raw text string of the response payload
data = response.json()     # Automatically parses JSON response into a dict!

# Passing parameters (e.g. ?q=python&page=2)
params = {'q': 'python', 'page': 2}
r = requests.get('https://api.example.com/search', params=params)

# Making a POST request (Sending data to server)
payload = {'user': 'alice', 'password': '123'}
r = requests.post('https://api.example.com/login', json=payload)
```

---

## 4. BeautifulSoup (Web Scraping)
Parses raw HTML so you can easily extract data. Usually paired with `requests`.

```python
from bs4 import BeautifulSoup
import requests

html_content = requests.get("https://example.com").text
soup = BeautifulSoup(html_content, 'html.parser')

# Finding elements
soup.title.text            # Get page title text
soup.find('h1')            # Find the FIRST <h1> tag
all_links = soup.find_all('a') # Find ALL <a> elements

# Extracting attributes and text
for link in all_links:
    url = link.get('href')   # Extract the 'href' attribute
    text = link.text         # Extract the text shown on the page

# Searching with classes and IDs
soup.find('div', class_='main-container')
soup.find(id='special-button')
```

---

## 5. Matplotlib & Seaborn (Data Visualization)
Visualizing data easily from standard arrays or pandas DataFrames.

```python
import matplotlib.pyplot as plt
import seaborn as sns

# Basic Matplotlib Line Graph
x = [1, 2, 3]
y = [10, 20, 15]
plt.plot(x, y)
plt.title("Sample Chart")
plt.xlabel("X Axis")
plt.ylabel("Y Axis")
plt.show()

# Seaborn capabilities (Great with pandas)
import pandas as pd
df = pd.DataFrame({'Category': ['A', 'B', 'A', 'B'], 'Value': [10, 20, 15, 25]})

# Creates an instant, highly styled box-plot grouping the categories
sns.boxplot(x='Category', y='Value', data=df)
plt.show()
```

---

## 6. Other Notable Libraries

| Library | Purpose | Brief Description |
| :--- | :--- | :--- |
| **`SQLAlchemy`** | Databases | Powerful Object Relational Mapper for interacting with SQL databases. |
| **`pytest`** | Testing | The industry standard for writing scalable and readable unit tests. |
| **`scikit-learn`**| Machine Learning | Accessible library for classification, regression, and clustering algorithms. |
| **`tqdm`** | Progress Bars | Wrap any iterable with `tqdm(iterable)` to see a live loading bar in the console. |
| **`FastAPI`** | Web Servers | Modern, fast web framework for building APIs with automatic documentation. |
| **`Pillow` (PIL)** | Image Processing | Opening, capturing, manipulating, and saving images in different formats. |

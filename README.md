# Free Python-10 WS Samples
Samples of Python code that can expedite any project. 
# 1. Web Scraping with BeautifulSoup and Selenium #
Web scraping is the process of extracting data from websites automatically. Python provides excellent libraries for web scraping, making it easy to retrieve information from web pages and store it in a structured format. Two widely used libraries for web scraping are BeautifulSoup and Selenium.
BeautifulSoup is a Python library that allows you to parse HTML and XML documents. It provides a simple and intuitive way to navigate and search the parsed data using various methods and selectors. BeautifulSoup is particularly useful for extracting data from static web pages.Here’s a simple example of using BeautifulSoup to scrape the titles of articles from a news website:

```bash
import requests
from bs4 import BeautifulSoup

# Send a GET request to the website
url = 'https://www.example.com/news'
response = requests.get(url)
# Create a BeautifulSoup object and parse the HTML
soup = BeautifulSoup(response.content, 'html.parser')
# Find all the article titles
titles = soup.find_all('h2', class_='article-title')
# Print the titles
for title in titles:
    print(title.text.strip())
```
Selenium, on the other hand, is a powerful tool for automating web browsers. It allows you to interact with web pages, fill out forms, click buttons, and extract data from dynamic websites that heavily rely on JavaScript. Selenium supports multiple web browsers and provides a flexible API for automating web interactions.Here’s an example of using Selenium to automate the login process on a website:

```bash
from selenium import webdriver
from selenium.webdriver.common.by import By

# Create a new instance of the Chrome driver
driver = webdriver.Chrome()
# Navigate to the login page
driver.get('https://www.example.com/login')
# Find the username and password input fields and enter the credentials
username_field = driver.find_element(By.ID, 'username')
username_field.send_keys('your_username')
password_field = driver.find_element(By.ID, 'password')
password_field.send_keys('your_password')
# Find and click the login button
login_button = driver.find_element(By.XPATH, '//button[@type="submit"]')
login_button.click()
# Close the browser
driver.quit()
```
These examples demonstrate the basic usage of BeautifulSoup and Selenium for web scraping and automation. Both libraries offer extensive functionality and can be used for more complex scraping tasks, such as handling pagination, dealing with dynamic content, and extracting data from APIs.
# 2. Task Automation with PyAutoGUI #

PyAutoGUI is a Python library that allows you to automate GUI-based tasks by controlling the mouse and keyboard. It provides a simple and intuitive API for simulating user interactions with graphical user interfaces.With PyAutoGUI, you can automate repetitive tasks such as filling out forms, clicking buttons, typing text, and taking screenshots. It supports cross-platform automation, making it compatible with Windows, macOS, and Linux. Here’s an example of using PyAutoGUI to automate a simple task of opening a text editor and typing a message:
```bash
import pyautogui
import time

# Wait for 2 seconds to allow the user to switch to the desired window
time.sleep(2)
# Open the text editor (assuming it's in the Applications folder on macOS)
pyautogui.press('command')
pyautogui.typewrite('space')
pyautogui.typewrite('textedit')
pyautogui.press('enter')
# Wait for the text editor to open
time.sleep(2)
# Type the message
pyautogui.typewrite('Hello, World!')
# Save the file
pyautogui.hotkey('command', 's')
pyautogui.typewrite('message.txt')
pyautogui.press('enter')
# Close the text editor
pyautogui.hotkey('command', 'q')
```
PyAutoGUI provides a wide range of functions for mouse and keyboard control, including moving the mouse, clicking, dragging, typing text, and pressing keys. It also offers image recognition capabilities, allowing you to locate and interact with specific graphical elements on the screen.PyAutoGUI is particularly useful for automating tasks that involve interacting with desktop applications or performing repetitive actions across multiple software tools.

# 3. Data Analysis Automation with Pandas #
Pandas is a powerful Python library for data manipulation and analysis. It provides data structures and functions that make it easy to work with structured data, such as tabular data in spreadsheets or SQL databases.With Pandas, you can automate various data analysis tasks, including data cleaning, transformation, filtering, aggregation, and visualization. It integrates well with other Python libraries, such as NumPy for numerical computing and Matplotlib for data visualization. Here’s an example of using Pandas to automate the analysis of a CSV file containing sales data:
```bash
import pandas as pd


# Read the CSV file into a DataFrame
df = pd.read_csv('sales_data.csv')
# Display the first few rows of the DataFrame
print(df.head())
# Calculate total sales by product category
sales_by_category = df.groupby('Category')['Sales'].sum()
print(sales_by_category)
# Filter the DataFrame to include only sales above a certain threshold
high_sales = df[df['Sales'] > 1000]
print(high_sales)
# Create a new column based on a condition
df['Discount'] = df['Price'].apply(lambda x: 0.1 if x > 50 else 0)
print(df.head())
# Save the modified DataFrame to a new CSV file
df.to_csv('updated_sales_data.csv', index=False)
```
In this very cool example, Pandas is used to read a CSV file into a DataFrame, which is a two-dimensional labeled data structure. We can then perform various operations on the DataFrame, such as displaying the first few rows, calculating total sales by product category, filtering rows based on a condition, creating new columns, and saving the modified data to a new CSV file. Pandas provides a wide range of functions for data manipulation, including merging, reshaping, and aggregating data. It also supports handling missing data, working with time series data, and performing statistical analysis. By leveraging Pandas, you can automate repetitive data analysis tasks, saving time and effort in processing and deriving insights from large datasets.

# 4. Test Automation with PyTest #
Test automation is crucial for ensuring the quality and reliability of software applications. Python offers several testing frameworks, and one of the most popular and feature-rich frameworks is PyTest.PyTest is a testing framework that makes it easy to write and run tests for Python code. It provides a simple and expressive syntax for defining test cases, assertions, and fixtures. PyTest supports various types of tests, including unit tests, integration tests, and functional tests. Here’s an example of using PyTest to automate the testing of a simple Python function:
```python
# calculator.py
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b
# test_calculator.py
import pytest
from calculator import add, subtract
def test_add():
    assert add(2, 3) == 5
    assert add(-1, 1) == 0
    assert add(0, 0) == 0
def test_subtract():
    assert subtract(5, 3) == 2
    assert subtract(-1, 1) == -2
    assert subtract(0, 0) == 0
def test_add_invalid_input():
    with pytest.raises(TypeError):
        add('2', 3)
def test_subtract_invalid_input():
    with
```
# 5. Demonstration: A Python Script for File Organization #
To illustrate the power of Python automation, let’s walk through a practical example of automating file organization. Imagine you have a folder filled with various files — documents, images, videos, etc. Manually sorting these files into appropriate subfolders can be a tedious task. However, with a Python script, we can automate this process effortlessly. Here’s a sample Python script that organizes files based on their file extensions:
```bash
import os
import shutil

# Define the main folder path
main_folder = "/path/to/your/folder"
# Create subfolders for different file types
subfolders = {
    "Documents": [".pdf", ".doc", ".docx", ".txt"],
    "Images": [".jpg", ".jpeg", ".png", ".gif"],
    "Videos": [".mp4", ".avi", ".mov"],
    "Audio": [".mp3", ".wav", ".aac"],
    "Others": []
}
# Iterate over files in the main folder
for filename in os.listdir(main_folder):
    file_path = os.path.join(main_folder, filename)
    
    # Check if it's a file (not a folder)
    if os.path.isfile(file_path):
        # Get the file extension
        _, extension = os.path.splitext(filename)
        
        # Determine the appropriate subfolder
        subfolder = "Others"
        for folder, extensions in subfolders.items():
            if extension.lower() in extensions:
                subfolder = folder
                break
        
        # Create the subfolder if it doesn't exist
        subfolder_path = os.path.join(main_folder, subfolder)
        os.makedirs(subfolder_path, exist_ok=True)
        
        # Move the file to the appropriate subfolder
        destination_path = os.path.join(subfolder_path, filename)
        shutil.move(file_path, destination_path)
        
        print(f"Moved {filename} to {subfolder} folder.")
```
Let’s review the script in detail :

•We import the necessary modules: 'os' for file and directory operations, and shutil for file movement.  
•We define the main_folder variable with the path to the folder containing the files to be organized.  
•We create a dictionary called subfolders that maps subfolder names to lists of corresponding file extensions. The "Others" subfolder is used for files with unspecified extensions.  
•We iterate over each file in the main_folder using os.listdir().  
•For each file, we check if it’s a file (not a folder) using os.path.isfile().  
•We extract the file extension using os.path.splitext().  
•We determine the appropriate subfolder by iterating over the subfolders dictionary and checking if the file extension matches any of the specified extensions.  
•If the subfolder doesn’t exist, we create it using os.makedirs() with exist_ok=True to avoid raising an error if the folder already exists.  
•Finally, we move the file to the appropriate subfolder using shutil.move() and print a message indicating the file movement.  
This script demonstrates how Python can automate the tedious task of organizing files based on their extensions. By running this script, all the files in the specified folder will be automatically sorted into the appropriate subfolders, saving you time and effort.  

# 6. Pandas samples #
Pandas is a popular Python library for data analysis, manipulation, and visualization. It provides a rich set of tools and functionalities that enable you to easily and effectively work with data in a variety of formats, including structured and unstructured data. In this article, we will provide a cheat sheet of common pandas operations and functions that you can use to quickly and efficiently perform data analysis in Python. 
To use Pandas for data analysis, you will need to import the Pandas library using the import statement, as follows:

![image](https://github.com/Blass2000/Python-WS-Samples/assets/89789502/44036c1b-dc92-43f6-9698-ccf9eab26bfd)

Once you have imported the Pandas library, you can use the following operations and functions to perform common data analysis tasks:
```bash
data.head()
```
•View the first few rows of a data frame. 
```bash
data.head()
```
•View the first few rows of a data frame. 
```bash
data.tail()
```
View the last few rows of a data frame
```bash
data.describe()
```
Compute summary statistics for numerical columns
```bash
data.info()
```
View the data types and memory usage of a data frame.
```bash
data.columns
```
View the columns of a data frame.
```bash
data['column']
```
Select a column of a data frame.
```bash
data.loc[row_index]
```
Select a row of a data frame by its index.
```bash
data.iloc[row_index]
```
Select a row of a data frame by its position.
```bash
data.dropna()
```
Drop rows with missing values.
```bash
data.fillna(value)
```
Fill missing values with a given value.
```bash
data.rename(columns={'old': 'new'})
```
Rename columns of a data frame.
```bash
data.sort_values(by='column')
```
Sort a data frame by the values of a column.
```bash
data.groupby('column')['column'].mean()
```
Group a data frame by the values of a column and compute the mean of another column.
```bash
data.plot.hist()
```
Plot a histogram of a numerical




Yeah, I know ther eis more to come 

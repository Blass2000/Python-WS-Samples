# Python-WS-Samples
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



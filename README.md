# GLAB-370.3.2-Read-CSV-into-Dictionary-or-List

## Lab Description
This lab focuses on understanding and reading a CSV (Comma-Separated Values) file into a dictionary or list in Python. CSV files are a common file format for storing tabular data, where each line represents a row and the values within a line are separated by commas or other delimiters. In this lab, learners will gain hands-on experience with reading CSV files, parsing the data, and storing it in a dictionary or list for further processing.

## Learning Objectives
Understand the structure of a CSV file and its data representation.
Learn how to read a CSV file in Python.
Parse the CSV data and store it in a dictionary or list.
Access and manipulate the data stored in the dictionary or list.
Apply the concepts learned to solve real-world scenarios.

## Prerequisites
Basic knowledge of Python programming.
Familiarity with data structures such as dictionaries and lists.

## Activities

### 1. Introduction to CSV
In this activity, you will be introduced to the CSV file format and its characteristics. CSV stands for Comma-Separated Values, and it is a plain text file format used for storing tabular data. Each line in a CSV file represents a row, and the values within a line are separated by commas or other delimiters.

The structure of a CSV file can be visualized as a table, where each line represents a row and each value represents a cell within the row. The first line of a CSV file typically contains the column names.

Here's an example of a CSV file representing a student's information:

```
Name,Age,Grade
John Doe,15,9
Jane Smith,14,8
```

### 2. Reading CSV into a Dictionary
In this activity, you will learn how to read a CSV file and store its data in a dictionary in Python. The csv module in Python provides functionality for working with CSV files.

To read a CSV file and store its data in a dictionary, you need to follow these steps:

- [ ] Import the csv module.
- [ ] Open the CSV file using the open() function.
- [ ] Create a CSV reader object using the csv.reader() function.
- [ ] Iterate over the rows in the CSV file and store the data in a dictionary.
- [ ] Close the file.

Here's an example that demonstrates reading a CSV file into a dictionary:

```
import csv

# Open the CSV file
with open('data.csv', newline='') as file:
    # Create a CSV reader object
    reader = csv.reader(file)

    # Initialize an empty dictionary
    data = {}

    # Iterate over the rows and store the data in the dictionary
    for row in reader:
        key = row[0]  # Assuming the first column is the key
        value = row[1:]  # Assuming the remaining columns are the values
        data[key] = value

# Print the data dictionary
print(data)
```

### 3. Reading CSV into a List of Dictionaries
In this activity, you will explore an alternative approach of reading a CSV file into a list of dictionaries. Instead of representing each row as a key-value pair in a single dictionary, you will represent each row as a separate dictionary and append them to a list.

To read a CSV file into a list of dictionaries, you can modify the previous example as follows:

```
import csv

# Open the CSV file
with open('data.csv', newline='') as file:
    # Create a CSV reader object
    reader = csv.DictReader(file)

    # Initialize an empty list
    data = []
    # Iterate over the rows and store each row as a dictionary in the list
for row in reader:
    data.append(row)
  Print the data list
    print(data)
```


In this example, we use the `csv.DictReader()` function to create a reader object that automatically treats the first row as the column names and each subsequent row as a dictionary, where the keys are the column names and the values are the corresponding cell values.

### 4. Real-world Scenario: Analyzing CSV Data

In this activity, you will apply your knowledge of reading CSV data into a dictionary or list to solve a real-world scenario. Imagine you are working with a sales data provider, and you have been given a CSV file that contains sales information for different products. Your task is to write a Python program that reads this CSV file, extracts relevant data, and performs specific operations on the data.

Here are the steps to complete this activity:

1. Open the CSV file using the `open()` function.
2. Create a CSV reader object using the `csv.DictReader()` function.
3. Extract the necessary data from the reader object and perform the required operations. For example, you might want to calculate the total sales or find the product with the highest sales.
4. Generate the desired output based on the operations performed.
5. Save and run your Python program to ensure it produces the correct output.
6. Submit your completed Python program as part of your lab submission.

```
import csv

# Open the CSV file
with open('sales_data.csv', newline='') as file:
    # Create a CSV reader object
    reader = csv.DictReader(file)

    # Extract relevant data and perform operations
    total_sales = 0
    max_sales = 0
    best_selling_product = ''

    for row in reader:
        product = row['Product']
        sales = int(row['Sales'])

        # Calculate the total sales
        total_sales += sales

        # Find the product with the highest sales
        if sales > max_sales:
            max_sales = sales
            best_selling_product = product

    # Generate the desired output
    print("Total Sales:", total_sales)
    print("Best Selling Product:", best_selling_product)
    
```

In this example, we assume that the sales data is stored in a CSV file named sales_data.csv, and each row represents a product's sales information, with columns for product name and sales.

You should modify the code according to the actual structure of the CSV file and the specific operations you need to perform on the data.

## Lab Submission
As part of this lab, you are required to complete the real-world scenario mentioned in Activity 4. Write a Python program that reads the CSV file, extracts the necessary data, performs the required operations, and generates the expected output. Submit your completed Python program file with appropriate comments and any additional instructions, if required.

Please ensure that your submitted program is well-documented and follows best practices for coding style and readability.

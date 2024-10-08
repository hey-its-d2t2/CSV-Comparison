

# CSV Comparison Service

## Overview

The CSV Comparison Service is a Spring Boot application that compares two CSV files and generates a detailed comparison report. The report identifies missing rows and highlights differences in values for matching rows. The results are saved in a result CSV file.

## Features

- Compares two CSV files and identifies missing rows.
- Highlights differences in values for matching rows.
- Generates a result CSV file with detailed comparison information.

## Technologies Used

- Java
- Spring Boot
- OpenCSV
- Apache POI

## Getting Started

### Prerequisites

- Java 11 or higher
- Maven
- Spring Boot
- OpenCSV library
- Apache POI library

### Installation

1. **Clone the repository:**

    ```bash
    git clone https://github.com/your-username/csv-comparison-service.git
    ```

2. **Navigate to the project directory:**

    ```bash
    cd csv-comparison-service
    ```

3. **Build the project using Maven:**

    ```bash
    mvn clean install
    ```

4. **Run the application:**

    ```bash
    mvn spring-boot:run
    ```

## API Documentation

### `GET /compare-csv`

Compares two CSV files and generates a comparison report.

#### Parameters

- `file1Path` (String): The file path of the first CSV file.
- `file2Path` (String): The file path of the second CSV file.
- `resultFilePath` (String): The file path where the result CSV file should be saved.
- `resultExcelPath` (String): The file path where the result Excel file should be saved.

#### Response

- **Success:**

    ```json
    {
      "message": "CSV files compared successfully. Results saved to /path/to/result.csv and /path/to/result.xlsx"
    }
    ```

- **Error:**

    ```json
    {
      "message": "Error during comparison: [errorMessage]"
    }
    ```

## Postman Testing Steps

1. **Open Postman.**
2. **Set the request type to `GET`.**
3. **Enter the URL for the endpoint, e.g.,** `http://localhost:8080/compare-csv`.
4. **In the `Params` section, add the following key-value pairs:**
   - `file1Path` = `/path/to/first.csv`
   - `file2Path` = `/path/to/second.csv`
   - `resultFilePath` = `/path/to/result.csv`
   - `resultExcelPath` = `/path/to/result.xlsx`
5. **Click `Send`.**

### Example Postman Request

**URL:**

```bash
http://localhost:8080/compare-csv?file1Path=/data/file1.csv&file2Path=/data/file2.csv&resultFilePath=/data/result.csv&resultExcelPath=/data/result.xlsx
```
## Code Decumentation

`CSVComparisonController.java`

This controller class handles the comparison of two CSV files and generates a comparison report in CSV and Excel formats.

### Methods
- `compareCSVFiles(String file1Path, String file2Path, String resultFilePath, String resultExcelPath)`

- **Description:** Compares two CSV files and writes the results to a CSV file and an Excel file. It identifies missing rows and differences in values.
- **Parameters:**
    - `file1Path` - Path to the first CSV file.
    - `file2Path` - Path to the second CSV file.
    - `resultFilePath` - Path where the result CSV file will be saved.
    - `resultExcelPath`- Path where the result Excel file will be saved.
- **Throws:**
    - **IOException** - If an I/O error occurs during file operations.
    - **CsvException** - If an error occurs while reading the CSV files.
    - **Returns:** A success message or an error message if an exception occurs.

- **createCellStyle(Workbook workbook, short color)**

    -  **Description:** Creates a `CellStyle` with a specific background color for the Excel sheet.
- **Parameters:**
    - **workbook** - The workbook in which the style will be used.
    - **color** - The index of the color to be applied.
    - **Returns:** A CellStyle with the specified background color.
 ## Contact
 For any questions or support, please contact deepsinghkumar01@gmail.com .



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

## Getting Started

### Prerequisites

- Java 11 or higher
- Maven
- Spring Boot
- OpenCSV library

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

### Compare CSV Files

**Endpoint:** `GET /compare-csv`

**Description:** Compares two CSV files and generates a comparison report.

**Request Parameters:**

- `file1Path` (String): The file path of the first CSV file.
- `file2Path` (String): The file path of the second CSV file.
- `resultFilePath` (String): The file path where the result CSV file should be saved.

**Example Request URL:**

```bash
http://localhost:8080/compare-csv?file1Path=/path/to/first.csv&file2Path=/path/to/second.csv&resultFilePath=/path/to/result.csv&resultFilePath=/data/result1.xlsx
```
**Response:**

- **Success:**

    ```json
    {
      "message": "CSV files compared successfully. Results saved to /path/to/result.csv"
    }
    ```

- **Error:**

    ```json
    {
      "message": "Error during comparison: [errorMessage]"
    }
    ```

**Postman Testing Steps**

1. Open Postman.
2. Set the request type to `GET`.
3. Enter the URL for the endpoint, e.g., `http://localhost:8080/compare-csv`.
4. In the `Params` section, add the following key-value pairs:
   - `file1Path` = `/path/to/first.csv`
   - `file2Path` = `/path/to/second.csv`
   - `resultFilePath` = `/path/to/result.csv`
   - `resultFilePath` = `/path/to/result.xlsx
5. Click `Send`.

**Example Postman Request**

**URL:**

```bash
http://localhost:8080/compare-csv?file1Path=/data/file1.csv&file2Path=/data/file2.csv&resultFilePath=/data/result.csv&resultFilePath=/data/result1.xlsx
```





# github_submissions_web_scrapping

# Web Scraping and CSV Validation Project

## Project Overview

- This project aims to automate the process of validating submissions for a hackathon by scraping GitHub repositories, identifying the correct CSV files, and ensuring they meet specific criteria. The solution handles various edge cases, including multiple CSV files, files with different formats (.csv and .xlsx), nested directories, and inaccessible repositories.

# Key Functionalities
- Web Scraping GitHub Repositories: The script accesses GitHub repositories to find CSV files.
- File Conversion: Converts .xlsx files to .csv format.
- Validation Against Criteria: Ensures the CSV files match specified column criteria.
- Handling Multiple and Nested Files: Traverses directories to find the most recent CSV file.
- Error Handling: Reports inaccessible repositories and invalid files.
- Output: Saves valid CSV files locally and provides detailed reports.

## Libraries Used
- requests: For making HTTP requests to GitHub's API to access repository contents.
- pandas: For handling and validating CSV and Excel data.
- io: For handling in-memory data streams.
- tempfile: For creating temporary files for converted data.
- urllib.parse: For parsing URLs.

# How It Works

## Checking URL Validity:

- The script checks if the provided URL is a valid GitHub repository URL.

## Accessing Repository Contents:

- Uses GitHub's API to fetch the contents of the repository.
- Handles authentication to manage API rate limits.

## Finding CSV and Excel Files:

- Traverses the repository contents, including nested directories, to find files with .csv or .xlsx extensions.
- Filters out files that do not meet the naming criteria (e.g., files containing "training" are excluded).

## Converting Excel Files:

- Converts .xlsx files to .csv format using pandas.
- Saves the converted files locally for further processing.

## Getting the Last Commit Date:

- Retrieves the last commit date for each file to identify the most recently modified file.

## Validating CSV Files:

- Reads the CSV file into a pandas DataFrame.
- Checks if the DataFrame's columns match the specified criteria (respondent_id, h1n1_vaccine, seasonal_vaccine).
- Only CSV files that match the criteria are considered valid.

## Reporting and Saving Valid CSVs:

- Keeps a count of valid CSV files found in each repository.
- Saves valid CSV files locally with a name based on the repository URL.

## Error Handling:

- Increments a counter for inaccessible repositories.
- Reports URLs that are not valid GitHub repositories.


# Conclusion
- This project demonstrates a robust solution for automating the validation of hackathon submissions by scraping GitHub repositories. It effectively handles multiple file formats, nested directories, and various error conditions. The use of pandas for data manipulation and requests for API interaction ensures that the solution is both powerful and flexible.

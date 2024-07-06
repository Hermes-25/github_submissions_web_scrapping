# Web Scraping and CSV Validation Project

This project involves scraping GitHub repositories to find the most recent `.csv` or `.xlsx` file, converting `.xlsx` files to `.csv`, and validating these files against a given criteria. The goal is to identify and process valid CSV files that match the required format.

## Prerequisites

1. **Python 3.x**: Ensure you have Python installed on your system.
2. **Required Libraries**: Install the necessary Python libraries using `pip`.

    ```sh
    pip install pandas requests openpyxl
    ```

3. **GitHub API Token**: Obtain a GitHub personal access token. This token allows you to make authenticated requests to the GitHub API, providing a higher rate limit.

## Project Structure

- `main.py`: The main script to run the project.
- `submission_format.csv`: The CSV file containing the required criteria (columns).
- `github_links.txt`: A text file containing the GitHub repository URLs to be processed.

## Running the Project

1. **Prepare the Input Files**:
    - `submission_format.csv`: This file should contain the column names required for the validation in the first row.
    - `github_links.txt`: List all GitHub repository URLs you want to process, each on a new line.

2. **Set Up the Environment**:
    - Ensure `main.py`, `submission_format.csv`, and `github_links.txt` are in the same directory.

3. **Run the Script**:
    - Execute the `main.py` script using your terminal or command prompt.

    ```sh
    python main.py
    ```

    The script will prompt you to enter your GitHub API token. You can also provide it directly in the script for convenience.

## Code Explanation

Here's a brief overview of what each part of the code does:

### Libraries

- `pandas`: Used for reading and processing CSV and Excel files.
- `requests`: Used for making HTTP requests to the GitHub API.
- `io`: Used for handling in-memory file objects.
- `tempfile`: Used for creating temporary files.
- `os`: Used for file path operations.

### Functions

- `get_repo_contents`: Fetches the contents of a given GitHub repository path.
- `get_last_commit_date`: Retrieves the date of the most recent commit for a given file path.
- `find_any_csv`: Searches for the most recent `.csv` or `.xlsx` file in a repository and converts `.xlsx` files to `.csv`.
- `validate_csv`: Validates the structure of a CSV file against the provided criteria.
- `process_repository`: Processes each repository URL, finds, and validates the most recent CSV file.

### Main Execution

- Reads the GitHub repository URLs from `github_links.txt`.
- Reads the criteria from `submission_format.csv`.
- Processes each repository, finds the most recent CSV file, validates it, and counts the number of valid CSV files.
- Outputs the result and saves valid CSV files.

## Example Usage

```sh
python main.py

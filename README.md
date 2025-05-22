# Canadian Job Market Analysis: Tech & Data Roles

This project analyzes wage data for various technology and data-related occupations in Canada. The data is sourced from the Government of Canada's open data API.

## Data Source

The data is fetched from the Government of Canada's open data API.
- **API Endpoint:** `https://open.canada.ca/data/en/api/3/action/datastore_search`
- **Resource ID:** `d16e10ea-77bf-4db8-bdb5-adc709e6cada`
- **Query Parameters Used:** `limit=100000` (to fetch a large number of records)

## Notebook Functionality (`job_analysis.ipynb`)

The Jupyter notebook `job_analysis.ipynb` performs the following key steps:

1.  **Data Fetching:** Retrieves job wage data from the specified `open.canada.ca` API endpoint.
2.  **Data Cleaning & Preprocessing:**
    *   Removes irrelevant columns (e.g., French titles, quartile wages, comments).
    *   Handles missing values by dropping rows with any NaNs.
3.  **Data Filtering:** Filters the dataset to include only predefined technology and data-related job titles.
4.  **Column Renaming:** Renames columns to be more descriptive and user-friendly (e.g., `NOC_Title_eng` to `Job_Title`).
5.  **Data Type Conversion:** Converts wage-related columns to numeric data types for analysis.
6.  **Wage Spread Calculation:** Computes the difference between the maximum and minimum hourly wages (`Max_Wage` - `Min_Wage`) for each job entry, creating a `Wage_Spread` column.
7.  **Data Visualization:**
    *   Generates a box plot to visualize and compare the distribution of `Wage_Spread` across the targeted job titles.
    *   Overlays a stripplot to show individual data points.
    *   The resulting plot is saved as `job_title_salary_comparison.png`.

## Target Job Roles

The analysis focuses on the following technology and data-related job titles:

-   Data scientists
-   Business development officers and market researchers and analysts
-   Business systems specialists
-   Computer systems developers and programmers
-   Software developers and programmers
-   Software engineers and designers
-   Web developers and programmers
-   User support technicians
-   Computer network technicians
-   Database analysts and data administrators
-   Information systems analysts and consultants

## Output

The primary output of this analysis is an image file named `job_title_salary_comparison.png`.

This plot is a horizontal box plot that displays:
-   The distribution of the wage spread (difference between maximum and minimum hourly wages) for each targeted job title.
-   Job titles are ordered by their median wage spread.
-   Individual data points are overlaid to provide a clearer view of the data distribution for each role.

This visualization helps in understanding and comparing the variability in wage ranges across different technology and data occupations in Canada based on the sourced data.

## How to Run

To run the analysis and generate the plot:

1.  **Prerequisites:**
    *   Python 3.x
    *   Jupyter Notebook or JupyterLab

2.  **Clone the Repository:**
    ```bash
    git clone <repository_url> # Replace <repository_url> with the actual URL
    cd <repository_directory>
    ```

3.  **Install Required Libraries:**
    The notebook uses the following Python libraries. If you don't have them installed, you can install them using pip:
    ```bash
    pip install pandas matplotlib seaborn numpy
    ```
    (Note: `urllib.request`, `ssl`, and `json` are part of the Python standard library.)

4.  **Run the Jupyter Notebook:**
    *   Start Jupyter Notebook or JupyterLab:
        ```bash
        jupyter notebook
        # or
        jupyter lab
        ```
    *   Open the `job_analysis.ipynb` notebook.
    *   Run all cells in the notebook.

5.  **View Output:**
    *   The output plot will be saved as `job_title_salary_comparison.png` in the root directory of the repository.
    *   The plot will also be displayed within the notebook.

## Contributing

Contributions are welcome! If you have suggestions for improvements, please feel free to:
1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/your-feature-name`).
3.  Make your changes.
4.  Commit your changes (`git commit -m 'Add some feature'`).
5.  Push to the branch (`git push origin feature/your-feature-name`).
6.  Open a Pull Request.

## License

This project is open source and available under the [MIT License](LICENSE). (Consider adding an MIT License file if you wish to formally license it).

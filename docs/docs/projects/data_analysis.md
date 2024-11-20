# Data Analysis

[Dataframe analysis tool in streamlit](https://dataframe.streamlit.app)

## 1. Purpose and Functionality
The application is designed for:

- **Reading and processing CSV and Excel files** from a specified directory.
- **Handling messy data** by extracting and analyzing emails, URLs, and words based on patterns.
- **Saving processed data** in user-specified formats (csv or pickle).

## 2. Key Components

### File Handling (FileHandler Class)
- `list_files(directory)`: Scans the given directory for files with `.csv`, `.xls`, or `.xlsx` extensions.
- `create_output_directory(directory)`: Creates an output subdirectory for saving processed files if it doesn’t already exist.

### Data Processing (DataProcessor Class)
- Utilizes regex patterns to extract:
  - **Emails** (`email_pattern`)
  - **URLs** (`url_pattern`)
  - **Words of specific lengths** (`word_pattern`)
- Enhances the original DataFrame by appending new columns containing extracted patterns.

### DataFrame Handling (DataFrameHandler Class)
- `read_file_to_dataframe(file_path, sheet_name)`: Reads data from CSV or Excel files. Supports multi-sheet reading for Excel files.
- `save_dataframe(df, filename, format)`: Saves the processed DataFrame in the chosen format (csv or pickle).

### Streamlit Application
Provides an intuitive interface for:
- **Inputting the directory path**
- **Selecting a file** from the available list
- **Viewing and previewing the DataFrame**
- **Defining the output filename and format** for saving processed data
- **Validating inputs** and offering real-time feedback via Streamlit widgets like `text_input`, `number_input`, and `selectbox`.

## 3. User Workflow

### File Selection
- The user specifies a directory path.
- The app lists available files, allowing the user to choose one by its index.

### DataFrame Operations
- If the selected file is an Excel file, the user can specify sheet names to read.
- The application loads the file into a DataFrame and displays a preview.

### Data Processing
- Data can be processed to include new columns containing extracted emails, URLs, and words.

### Save Options
- The user can specify an output filename and format (csv or pickle).
- The processed data is saved in an automatically created output subdirectory.
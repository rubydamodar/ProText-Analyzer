# 📝 ProText-Analyzer

**Objective**:  
The **ProText-Analyzer** project extracts article content from provided URLs and performs various text analysis tasks like sentiment scoring, readability measurement, and more. The results are structured in a clean and organized format, ready for review and further use.

## Project Overview

The goal of **ProText-Analyzer** is to:
1. **Extract Textual Data**: Fetch the article content from URLs provided in the `Input.xlsx` file.
2. **Perform Textual Analysis**: Calculate the following metrics:
   - Sentiment scores (positive, negative, polarity, subjectivity)
   - Readability scores (Fog Index, Avg. Sentence Length)
   - Word count, syllable count, and other word statistics

---

## Technologies Used

- **Python** 🐍
   - Libraries:
     - `TextBlob` for sentiment analysis
     - `spaCy` for text processing tasks (tokenization, POS tagging, etc.)
     - `Syllapy` for syllable counting
     - `BeautifulSoup` for HTML parsing during data extraction
     - `Requests` for handling HTTP requests
- **Pandas** for data management
- **Excel/CSV** for input/output handling

---

## Installation

1. Clone the repository to your local machine:
   ```bash
   git clone https://github.com/rubydamodar/ProText-Analyzer.git
   cd ProText-Analyzer
   ```

2. Install the required Python libraries:
   ```bash
   pip install -r requirements.txt
   ```

---

## Data Extraction Process

The **ProText-Analyzer** extracts the article title and body from each URL listed in the `Input.xlsx` file and stores the text for further analysis.

### Process Overview:
1. **Read Input File**: Load the URLs and their associated IDs from `Input.xlsx`.
2. **Extract Article Content**:
   - Fetch HTML content using `requests`.
   - Parse the HTML using `BeautifulSoup` to extract the article's title and body.
   - Save the extracted content into text files named after the `URL_ID`.

### File Management:
- Each article's content is saved in text files, facilitating a clean process for further analysis.
- Error handling ensures proper management of file I/O and network issues.

---

## Text Analysis Process

The extracted text undergoes several analysis steps to compute the following variables:

1. **Sentiment Analysis**:
   - Implemented using `TextBlob` to compute **Positive Score**, **Negative Score**, **Polarity Score**, and **Subjectivity Score**.
   - Text is cleaned by removing stop words and irrelevant characters.

2. **Readability Analysis**:
   - Calculated using the Gunning Fog Index.
   - Additional metrics: **Average Sentence Length**, **Percentage of Complex Words**, and **Fog Index**.

3. **Word-Level Metrics**:
   - **Word Count**, **Complex Word Count**, **Syllable Count per Word** (via `syllapy`), **Personal Pronouns Count** (using regex), and **Average Word Length**.

---

## Output Structure

The results are saved in **Excel/CSV** format as per the structure outlined in `Output Data Structure.xlsx`. The following variables are included:
- Positive Score
- Negative Score
- Polarity Score
- Subjectivity Score
- Average Sentence Length
- Complex Word Count
- Word Count
- Syllable Count
- Personal Pronouns Count
- Average Word Length

---

## How to Run

1. **Data Extraction**:
   Run the script to extract article data from the URLs:
   ```bash
   python data_extraction.py
   ```

2. **Text Analysis**:
   Run the text analysis script to process the extracted articles:
   ```bash
   python text_analysis.py
   ```

The results will be saved in the output directory in `.csv` or `.xlsx` format.

---

## Challenges and Solutions

- **Error Handling**: Implemented robust error handling to manage potential network and file-related issues.
- **Text Processing**: Utilized advanced tools like `spaCy` for precise text tokenization and POS tagging, and `syllapy` for syllable counting.
- **Personal Pronouns**: Regex was used to accurately capture pronouns without including words like "US" mistakenly.

---

## Contributing

We welcome contributions to enhance **ProText-Analyzer**! To contribute:
1. Fork the repository.
2. Create a new branch for your changes.
3. Submit a pull request with a detailed description of your changes.

---

## License

This project is licensed under the [MIT License](LICENSE).

---

### Project Maintainer
Ruby Poddar  
Email: rubypoddarr@gmail.com 



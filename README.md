# Biopharma Research Paper Fetcher

**Author:** Abhinit Sundar  
**Email:** aks94@njit.edu  

## Overview

This project provides a command-line tool to fetch and filter PubMed research papers. It is designed to extract papers with **at least one non-academic author affiliated with biotech/pharmaceutical companies**, excluding institutional or academic affiliations.

## Features

- Query PubMed using full advanced syntax
- Extract metadata from MEDLINE format:
  - PubMed ID
  - Title
  - Publication Year
  - Non-academic Author(s)
  - Company Affiliation(s)
  - Corresponding Author Email
- Filters out academic or institutional affiliations
- Outputs structured CSV reports
- CLI interface via `poetry run`
- Fully typed, modular, and maintainable code

## Technologies

- Python 3.9+
- [Biopython](https://biopython.org/)
- [Pandas](https://pandas.pydata.org/)
- [TQDM](https://tqdm.github.io/)
- Poetry for dependency and packaging management

## Installation

```bash
# Install Poetry
curl -sSL https://install.python-poetry.org | python3 -

# Clone the repository
git clone https://github.com/asundar0128/ResearchPapersQuery.git
cd ResearchPapersQuery/pubmed_fetcher_project

# Install dependencies
poetry install
```

## Usage

Run the CLI with your PubMed query:

```bash
poetry run get-papers-list "(pharmaceutical OR biotech OR life sciences) AND affiliation[Affiliation]" -f filteredPubMedArticles.csv
```

Enable debug mode to see detailed log output:

```bash
poetry run get-papers-list "pharma AND affiliation[Affiliation]" -d
```

## Sample Output

```csv
PubmedID,Title,Publication Date,Non-academic Author(s),Company Affiliation(s),Corresponding Author Email
12345678,Innovative Drug Targeting,2022,John Doe; Jane Smith,ABC Biotech; XYZ Pharma,john.doe@abcbiotech.com
```

## Test Query Example

```bash
poetry run get-papers-list "(pharmaceutical OR biotech OR drug development) AND affiliation[Affiliation]" -f filteredPubMedArticles.csv
```

## Results

- Total Articles Fetched: 55  
- Articles with Corporate Affiliations: 55  

## License

This project is open source and licensed under the MIT License.

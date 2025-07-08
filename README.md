# ResearchPapersQuery

1.
   a. Code organized with dependencies installation for Poetry package followed by core filtering logic with corporate and institutional keywords
   b. Retrieving author's corresponding email address from record with field data
   c. Specific functions for fetching details, processing records, and retrieving publication year for the PubMed database using a query and maximum results
   d. Command line interface with parsing logic for supporting a user-defined PubMed query string
   e. Installing poetry package and get-papers-list with pharmaceutical, biotech, drug development, biopharma, medical, and life sciences
   f. Output File: filteredPubMedArticles.csv (attached in GitHub)

2. Install dependencies with the following commands:

!curl -sSL https://install.python-poetry.org | python3 -

import os

os.environ["PATH"] += ":/root/.local/bin" 

!pip install biopython

!poetry new pubmed_fetcher_project --src

%cd pubmed_fetcher_project

!poetry install

!poetry run get-papers-list "(pharmaceutical OR biotech OR biotechnology OR pharma OR drug development OR biopharmaceutical OR life sciences OR medical company) AND (affiliation[Affiliation])" -f filteredPubMedArticles.csv

3. Tools (LLMs or Libraries Used to Build the Program)
   https://chatgpt.com/c/686d750f-b280-800e-8e98-f4632d5a1147 - link to ChatGPT prompts
   pubmed_fetcher.core with search_pubmed, fetch_details, process_records
   Bio, biopython, tqdm, typing, re

# ResearchPapersQuery

1. Install dependencies with the following commands: 
!curl -sSL https://install.python-poetry.org | python3 -
import os
os.environ["PATH"] += ":/root/.local/bin" 
!pip install biopython
!poetry new pubmed_fetcher_project --src
%cd pubmed_fetcher_project
!poetry install
!poetry run get-papers-list "(pharmaceutical OR biotech OR biotechnology OR pharma OR drug development OR biopharmaceutical OR life sciences OR medical company) AND (affiliation[Affiliation])" -f filteredPubMedArticles.csv

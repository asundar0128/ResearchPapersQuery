# ResearchPapersQuery - PubMed Fetcher CLI

A Python CLI tool for retrieving **PubMed articles** with **non-academic authors** affiliated with **pharmaceutical, biotech, life sciences, and medical companies**. Built using Poetry for dependency management and packaged for easy command-line use.

---

## Features for PubMed Program

- Supports full **PubMed query syntax**
- Filters articles by **corporate vs. academic affiliation**
- Extracts **PubMed ID, title, publication year, non-academic authors, company affiliations, and corresponding author email**
- Outputs results in **CSV format**

---

## Query Used for PubMed Fetcher Project

```bash
!poetry run get-papers-list "(pharmaceutical OR biotech OR biotechnology OR pharma OR drug development OR biopharmaceutical OR life sciences OR medical company) AND (affiliation[Affiliation])" -f filteredPubMedArticles.csv


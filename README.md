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
40334840,Colistin-resistant Klebsiella pneumoniae species complex: The scenario in Mexico.,2025 Jun,Rodriguez-Santiago, Jonathan; Alvarado-Delgado, Alejandro; Rodriguez-Medina, Nadia; Garza-Gonzalez, Elvira; Tellez-Sosa, Juan; Duarte-Zambrano, Luis; Nava-Dominguez, Neli; Sohlenkamp, Christian; Vences-Guzman, Miguel A; Lopez-Jacome, Luis Esau; Morfin-Otero, Rayo; Rodriguez-Noriega, Eduardo; Hernandez-Castro, Rigoberto; Mireles-Davalos, Christian,Programa de Doctorado en Ciencias Biomedicas, Universidad Nacional Autonoma de Mexico, Cuernavaca, Morelos, Mexico; Instituto Nacional de Salud Publica, Centro de Investigacion sobre Enfermedades Infecciosas, Grupo de Investigacion y Docencia en Resistencia Antimicrobiana, Cuernavaca, Morelos, Mexico; Facultad de Medicina Veterinaria y Zootecnia, Universidad Autonoma de Chiapas, Current affiliation. Tuxtla Gutierrez, Chiapas, Mexico.; Instituto Nacional de Salud Publica, Centro de Investigacion sobre Enfermedades Infecciosas, Grupo de Investigacion y Docencia en Resistencia Antimicrobiana, Cuernavaca, Morelos, Mexico.; Instituto Nacional de Salud Publica, Centro de Investigacion sobre Enfermedades Infecciosas, Grupo de Investigacion y Docencia en Resistencia Antimicrobiana, Cuernavaca, Morelos, Mexico.; Facultad de Medicina, Universidad Autonoma de Nuevo Leon, Monterrey, Nuevo Leon, Mexico.; Instituto Nacional de Salud Publica, Centro de Investigacion sobre Enfermedades Infecciosas, Grupo de Investigacion y Docencia en Infeccciones Cronicas y Cancer, Cuernavaca, Morelos, Mexico.; Instituto Nacional de Salud Publica, Centro de Investigacion sobre Enfermedades Infecciosas, Grupo de Investigacion y Docencia en Resistencia Antimicrobiana, Cuernavaca, Morelos, Mexico.; Instituto Nacional de Salud Publica, Centro de Investigacion sobre Enfermedades Infecciosas, Grupo de Investigacion y Docencia en Resistencia Antimicrobiana, Cuernavaca, Morelos, Mexico.; Centro de Ciencias Genomicas, Universidad Nacional Autonoma de Mexico, Cuernavaca, Morelos, Mexico.; Centro de Ciencias Genomicas, Universidad Nacional Autonoma de Mexico, Cuernavaca, Morelos, Mexico.; Instituto Nacional de Rehabilitacion Luis Guillermo Ibarra Ibarra, Ciudad de Mexico, Mexico.; Instituto Nacional de Enfermedades Respiratorias, Ciudad de Mexico, Mexico.; Instituto Nacional de Enfermedades Respiratorias, Ciudad de Mexico, Mexico.; Centro Medico Nacional Siglo XXI, IMSS, Ciudad de Mexico, Mexico.; Instituto Nacional de Salud Publica, Centro de Investigacion sobre Enfermedades Infecciosas, Grupo de Investigacion y Docencia en Resistencia Antimicrobiana, Cuernavaca, Morelos, Mexico., ulises.garza@insp.mx.
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

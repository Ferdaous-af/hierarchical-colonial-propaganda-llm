# A Hierarchical LLM Workflow for Detecting Colonial Propaganda in Historical Newspapers

This repository contains the computational notebook and supporting reproducibility materials associated with the DH2026 contribution:

**Ferdaous Affan (2026). “A Hierarchical LLM Workflow for Detecting Colonial Propaganda in Historical Newspapers: the Case of the Perdicaris Affair (1904).”**

## Research overview

This project investigates how large language models can support the identification and analysis of colonial propaganda in historical newspapers without reducing propaganda to sentiment or a single binary classification.

The workflow applies a hierarchical analytical framework comprising three levels:

1. **Ideological frames**
   - Legitimization
   - Demonization
   - Naturalization

2. **Rhetorical mechanisms**
   - Authority Appeal
   - Moral or Duty Appeal
   - Exemplification
   - Fear Appeal
   - Labeling
   - State Failure Framing
   - Essentialization
   - Normalization
   - Selective Framing

3. **Historical tropes**
   - Period-specific expressions and representations
   - Links between tropes, frames, and rhetorical mechanisms
   - Verbatim textual evidence in the original language

The case study examines newspaper coverage of the 1904 Perdicaris Affair using material retrieved through the [Impresso Media Monitoring of the Past](https://impresso-project.ch/app) Web App.

## Workflow

The notebook implements four stages:

1. **Article relevance classification and propaganda detection**
   - Relevance categories: `CORE`, `RELATED`, `PERIPHERAL`, and `UNRELATED`
   - Binary propaganda detection
   - Confidence scores and short justifications

2. **Propaganda intensity assessment**
   - Density
   - Explicitness
   - Emotional impact
   - Composite intensity rating

3. **Frame and mechanism identification**
   - Assignment of ideological frames
   - Detection of rhetorical mechanisms
   - Extraction of supporting evidence spans
   - Recording of confidence scores and mechanism subtypes

4. **Historical trope extraction**
   - Identification of period-specific vocabulary
   - Expansion of an initial trope list
   - Links between tropes, frames, and mechanisms
   - Contextual information concerning rhetorical strategy, historical context, target audience, and ideological framework

The workflow links model classifications to evidence spans in the original French or German text. It is designed to support iterative movement between computational analysis and source-aware close reading.

## Associated publication

This repository accompanies the following published abstract:

> Affan, Ferdaous (2026): “A Hierarchical LLM Workflow for Detecting Colonial Propaganda in Historical Newspapers: the Case of the Perdicaris Affair (1904)”, in: *Digital Humanities 2026: Book of Abstracts*. ADHO Digital Humanities Conference 2026 (DH2026), Daejeon Convention Center. DOI: [10.5281/zenodo.21495909](https://doi.org/10.5281/zenodo.21495909).


## Repository structure

```text
dh2026-colonial-propaganda-llm/
│
├── README.md
├── CITATION.cff
├── LICENSE
├── LICENSE-CONTENT.md
├── .gitignore
├── requirements.txt
│
├── notebooks/
│   └── hierarchical_llm_colonial_propaganda_workflow.ipynb
│
├── data/
│   └── README.md


### Main files

- `notebooks/`: Main Jupyter notebook implementing the workflow.
- `data/`: Documentation of corpus construction, access conditions, and expected input structure.
- `requirements.txt`: Python dependencies required to run the notebook.
- `CITATION.cff`: Machine-readable citation metadata.
- `LICENSE`: GNU General Public License v3.0 for software code.
- `LICENSE-CONTENT.md`: Creative Commons licence for original non-code material.
- `.gitignore`: Files and folders that should not be committed to the repository.

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/dh2026-colonial-propaganda-llm.git
cd dh2026-colonial-propaganda-llm
```

Replace `YOUR-USERNAME` with the GitHub username under which the repository is published.

Alternatively, download the repository as a ZIP file from GitHub.

### 2. Create a virtual environment

```bash
python -m venv .venv
```

Activate it on Linux or macOS:

```bash
source .venv/bin/activate
```

Activate it on Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

### 3. Install the dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure the OpenAI API key

Do not place an API key directly in the notebook.

Set it as an environment variable.

Linux or macOS:

```bash
export OPENAI_API_KEY="your-api-key"
```

Windows PowerShell:

```powershell
$env:OPENAI_API_KEY="your-api-key"
```

The notebook retrieves the key using:

```python
import os

api_key = os.getenv("OPENAI_API_KEY")

if not api_key:
    raise RuntimeError(
        "The OPENAI_API_KEY environment variable has not been configured."
    )
```

### 5. Open the notebook

Start Jupyter:

```bash
jupyter notebook
```

Then open:

```text
notebooks/hierarchical_llm_colonial_propaganda_workflow.ipynb
```

## Computational requirements

The notebook requires access to the OpenAI API.

API use may generate costs. Outputs may vary because of:

- model updates;
- API changes;
- prompt modifications;
- stochastic variation;
- changes to the input corpus;
- changes to package versions.

The notebook records the model and parameters used for the DH2026 analysis where possible.

## Data

The corpus was retrieved through the Impresso Media Monitoring of the Past Web App using the keyword query:

```text
Perdicaris
```

The initial corpus comprises 360 French- and German-language newspaper items published between 20 May 1904 and 2 March 1909.

The workflow assigns each item one of four relevance categories:

- `CORE`
- `RELATED`
- `PERIPHERAL`
- `UNRELATED`

Following relevance classification, 305 items classified as `CORE` or `RELATED` were retained for the principal analysis.

The complete newspaper texts are not redistributed through this repository. Access to the source material remains subject to the rights, licences, terms of use, and access conditions established by Impresso and its contributing institutions.

## Citation

### Citing the research

When referring to the research framework, methodology, analysis, or findings, please cite the published DH2026 abstract:

> Affan, Ferdaous (2026): “A Hierarchical LLM Workflow for Detecting Colonial Propaganda in Historical Newspapers: the Case of the Perdicaris Affair (1904)”, in: *Digital Humanities 2026: Book of Abstracts*. ADHO Digital Humanities Conference 2026 (DH2026), Daejeon Convention Center. DOI: [10.5281/zenodo.21495909](https://doi.org/10.5281/zenodo.21495909).

### Citing the implementation

When referring specifically to the notebook, prompts, source code, or a particular implementation version, please also cite this GitHub repository.

Machine-readable citation information is available in [`CITATION.cff`](CITATION.cff). GitHub may also display a **Cite this repository** option in the repository sidebar.

## Licensing

This repository uses separate licences for software and scholarly content.

### Software

Software, scripts, functions, and notebook code cells are licensed under the **GNU General Public License v3.0**.

See [`LICENSE`](LICENSE).

### Original non-code content

Unless otherwise indicated, original documentation, prompts, diagrams, figures, Markdown text, and analytical commentary are licensed under the **Creative Commons Attribution Non Commercial No Derivatives 4.0 International Licence**.

See [`LICENSE-CONTENT.md`](LICENSE-CONTENT.md).

### Third-party material

The repository licences do not apply to:

- newspaper articles;
- OCR text obtained through Impresso;
- newspaper images;
- third-party metadata;
- source material supplied by contributing institutions;
- cited publications;
- third-party logos, trademarks, or visual identities;
- the DH2026 Book of Abstracts;
- material otherwise identified as belonging to another rights holder.

Such material remains subject to its original copyright, licence, terms of use, and access conditions.

## Responsible use

The workflow is intended to support historical research and interpretation. Model outputs should not be treated as definitive classifications without examination of the underlying sources.

Researchers using or adapting the workflow should:

- inspect the source evidence linked to model outputs;
- document changes to prompts, taxonomies, models, and parameters;
- assess language- and source-specific limitations;
- avoid treating model confidence as equivalent to historical certainty;
- respect the rights and access conditions of source collections;
- report substantial methodological modifications when publishing derived work.

## Author

**Ferdaous Affan**

Luxembourg Centre for Contemporary and Digital History  
University of Luxembourg  
Luxembourg

Email: [ferdaous.affan@uni.lu](mailto:ferdaous.affan@uni.lu)
````

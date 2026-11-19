# SeedBox

[![Open Science](https://img.shields.io/badge/Open%20Science-free%20software-F68212?logo=openaccess&logoColor=white)](#open-science)
[![License: MIT](https://img.shields.io/badge/License-MIT-3DA639?logo=opensourceinitiative&logoColor=white)](LICENSE)
[![INPI](https://img.shields.io/badge/INPI-BR512026011133--1-1f6feb)](#inpi-registration)
![Version](https://img.shields.io/badge/version-2.01-2EA043)
![Platform](https://img.shields.io/badge/platform-Windows%2010%20%7C%2011-0078D6)

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/f5b80a34-5ef5-4fe8-a976-20b609186eea" />

**A user-friendly software package for high-throughput seed morphometry modelling for quantitative plant ecology**

SeedBox: Dimensional Morphometry is academic software for the dimensional morphometry of seeds. From three linear measurements of each seed (length, width and thickness) it computes the derived physical properties, compares treatments or populations, describes the multivariate structure of the data and uses machine learning to assess how well the seed lots can be told apart.

SeedBox is intended for researchers, lecturers and students in seed science, ecology, restoration and forest breeding.

## Key features

- Import of Excel and CSV spreadsheets with automatic column recognition, or direct data entry.
- Per-seed computation of arithmetic and geometric mean diameter, surface area, volume, aspect ratio and sphericity index.
- Comparison of two or more treatments/populations with automatic selection of the statistical test, effect sizes and grouping letters.
- Correlations, principal component analysis, unsupervised clustering and self-organizing map.
- Eight classifiers evaluated by repeated cross-validation, with identification of the best model and a permutation test.
- Eleven publication-quality figures (up to 1200 dpi), PDF report, ZIP figure package and an Excel workbook with all results.
- Interface in Portuguese and English.

## Download and installation

1. Download `SeedBox_2.01_Setup.exe` from the [Releases](https://github.com/Montcharles/SeedBox/releases) page.
2. Run the installer and choose the installation language. SeedBox is installed in your user profile (`%LOCALAPPDATA%\Programs\SeedBox`), without administrator rights, and shortcuts are created on the desktop and in the Start menu.
3. The installer is not digitally signed, so Windows SmartScreen may display the message **"Windows protected your PC"**. Click **More info** and then **Run anyway** to continue.

To uninstall, use **Uninstall SeedBox** in the Start menu or remove SeedBox under **Settings > Apps** in Windows.

## System requirements

| Item | Requirement |
|---|---|
| Operating system | Windows 10 or Windows 11, 64-bit |
| Disk space | About 400 MB |
| Memory | 4 GB RAM (8 GB recommended) |
| Display | Minimum resolution 1280 × 720 |
| Permissions | No administrator rights required |
| Internet connection | Not required |

## User manual

User manuals in English and Portuguese (PDF) are available on the [Releases](https://github.com/Montcharles/SeedBox/releases) page.

## Input data

- **File formats:** Excel (.xlsx, .xlsm) or delimited text (.csv, .txt). The column separator and the decimal comma are detected automatically.
- **Layout:** one row per seed, with length, width and thickness in millimetres and a grouping column (treatment, population or lot).
- **Column names** are recognised in English and Portuguese, regardless of accents and capitalisation (e.g., length/comprimento, width/largura, thickness/espessura, treatment/tratamento, population/população, lot/lote). If a column is not recognised, a mapping dialog lets you assign it manually.
- **One sheet per lot:** in a workbook without a grouping column, each sheet is treated as a lot and named after the sheet.
- **Manual entry:** a data table can be generated for up to 30 treatments or populations and 3 to 5000 seeds per lot, and values can be typed or pasted from a spreadsheet.
- **Template and example:** the Data page offers a spreadsheet template (**Download template**) and an example dataset (**Example dataset**).

Example of the expected layout:

| Lot | Length (mm) | Width (mm) | Thickness (mm) |
|---|---|---|---|
| Population A | 12.91 | 6.85 | 4.74 |
| Population A | 13.40 | 7.02 | 4.51 |
| Population B | 11.87 | 6.63 | 4.96 |

By convention, length is the major axis, width the intermediate axis and thickness the minor axis of the seed.

## Physical properties

Seeds are treated as ellipsoids, following Mohsenin (1986). For each seed, SeedBox computes:

| Property | Symbol | Equation | Unit |
|---|---|---|---|
| Arithmetic mean diameter | $D_a$ | $(L + W + T)/3$ | mm |
| Geometric mean diameter | $D_g$ | $(L W T)^{1/3}$ | mm |
| Aspect ratio | $R$ | $(W/L) \times 100$ | % |
| Sphericity index | $\Phi$ | $(D_g/L) \times 100$ | % |
| Volume | $V$ | $\pi L W T/6$ | mm³ |
| Surface area | $S$ | $\pi D_g^2$ | mm² |

where $L$, $W$ and $T$ are the length, width and thickness of the seed.

## Reproducibility

All random procedures (cross-validation partitions, classifiers, permutation tests and self-organizing map) use a fixed random seed, 42 by default, which can be changed under **Settings > Random seed**. Repeating an analysis of the same data with the same settings yields identical results.

## Open science

SeedBox is free software, distributed at no cost under the MIT License, an open-source license approved by the Open Source Initiative, and its source code is available in this repository. The program runs offline, without registration or license keys, its analyses are reproducible (see [Reproducibility](#reproducibility)), and all results can be exported to a spreadsheet so that they can be checked, reused and shared.

## Technology and third-party software

SeedBox is written in Python 3.12, with a C++17 computational core for the derivation of physical properties, the training of the self-organizing map and the χ² permutation test. It is built on the following open-source components, whose license texts are distributed with the installed program:

| Component | Version | License |
|---|---|---|
| Python | 3.12 | PSF License |
| NumPy | 2.5.4 | BSD-3-Clause |
| SciPy | 1.18.1 | BSD-3-Clause |
| pandas | 3.1.0 | BSD-3-Clause |
| scikit-learn | 1.9.1 | BSD-3-Clause |
| Matplotlib | 3.11.2 | Matplotlib License (PSF-based) |
| PySide6 (Qt for Python) | 6.9.3 | LGPL-3.0 |
| ReportLab | 5.1.0 | BSD License |
| openpyxl | 3.1.5 | MIT |

## INPI registration

The registration of SeedBox with the Brazilian National Institute of Industrial Property (INPI) was carried out as part of the activities of the course *Employability and Innovation in the Biologist's Profession* of the undergraduate program in Biological Sciences at the Universidade Estadual de Mato Grosso do Sul (UEMS).

| | |
|---|---|
| Process number | BR512026011133-1 |
| Filing date | 19 November 2026 |
| Holder | Montcharles da Silva Pontes |
| Registered title | SeedBox: A user-friendly software package for high-throughput seed morphometry modelling for quantitative plant ecology |

## How to cite

If you use SeedBox, please cite the software and the methodological article. The **Cite this repository** button on this page provides the software citation in APA and BibTeX formats.

**Software**

Holsback, Z. R., Rosa, V. H. V., Santos Junior, T. R., Higa Junior, C., Tagino, D. A. C., Barbosa, G. M., Moreno, Y. A., Silva, A. L. F., Silva, A. L. N., Figueiredo, N. S., Costa, G. C., Nabuco, M. L. H. P., Mascarenhas, A. H., Casprechen, E. C. K., Escobar, Y. M. B., Vitorino, S. M. S., Liberato, A. L. B., Milaneze, A. M. I., Soares, A. R. S., Miranda, A. S., Vasques, A. B. M., Silva, E. B., Brito, P. V. L., Santos, R. B., Bolssonaro, R. C., Benites, A. D., Mazuchelli, I. P. S., Zubieta, A. J. A. S., Valerio, Y. V., Jesus, A. A., & Pontes, M. S. (2026). *SeedBox: A user-friendly software package for high-throughput seed morphometry modelling for quantitative plant ecology* (Version 2.01) [Computer software]. INPI registration application BR512026011133-1. https://github.com/Montcharles/SeedBox

**Methodological article**

The methodology follows the reference article by Nobrega et al. (2026), published in *Flora*, which applied this protocol to discriminate *Schizolobium parahyba* populations from the Cerrado and the Atlantic Forest.

Nobrega et al. (2026). A simple method for discriminating *Schizolobium parahyba* (Vell.) Blake (Fabaceae) seeds population by dimensional morphometry and machine learning algorithms. *Flora*, 153108. ISSN 0367-2530. https://doi.org/10.1016/j.flora.2026.153108

## Support

Questions, bug reports and suggestions can be submitted through the [Issues](https://github.com/Montcharles/SeedBox/issues) page of this repository.

## License

SeedBox is distributed under the [MIT License](LICENSE).

## References

Mohsenin, N. N. (1986). *Physical properties of plant and animal materials* (2nd ed.). Gordon and Breach Science Publishers.

Pontes et al. (2018). High-throughput phenotyping by applying digital morphometrics and fluorescence induction curves in seeds to identifying variations: A case study of *Annona* (Annonaceae) species. *Information Processing in Agriculture*, 5, 443–455. https://doi.org/10.1016/j.inpa.2018.07.001

Nobrega et al. (2026). A simple method for discriminating *Schizolobium parahyba* (Vell.) Blake (Fabaceae) seeds population by dimensional morphometry and machine learning algorithms. *Flora*, 153108. ISSN 0367-2530. https://doi.org/10.1016/j.flora.2026.153108

# FoldX-Mutational-Profile-Analyzer
GUI tool for parsing FoldX .fxout output files, computing per-amino-acid ΔΔG statistics, and identifying stabilizing mutations. Exports results to Excel and displays a color-coded thermodynamic mutational profile chart. Built with Python, Tkinter, Pandas, and Matplotlib.
Here's a README for the project:

---

# FoldX Mutational Profile Analyzer

A Python desktop application for analyzing and visualizing FoldX protein stability data.

## Features

- Import `.fxout` files from FoldX output
- Automatically parses wild-type and mutant interaction energies
- Calculates ΔΔG values for all 20 amino acids
- Flags ideal mutation candidates (ΔΔG < −0.5 kcal/mol)
- Exports results to a structured `.xlsx` workbook (summary + detailed sheets)
- Displays a color-coded thermodynamic mutational profile bar chart

## Requirements

```
pandas
numpy
matplotlib
openpyxl
```

Install dependencies with:

```bash
pip install pandas numpy matplotlib openpyxl
```

## Usage

1. Run the application:
```bash
python foldx_analyzer.py
```
2. Click **Import a file** and select your `.fxout` file
3. Click **Start the analysis & Create an Excel**
4. The Excel file is saved in the same directory as the input file
5. A mutational profile chart is displayed automatically

## Output

| Sheet | Contents |
|---|---|
| `Ozet_Analiz` | Per-amino-acid mean ΔΔG, STDEV, SEM, and decision label |
| `Hesaplama_Detaylari` | Full run-by-run breakdown of mutant vs. wild-type energies |

## Threshold

Mutations with a mean ΔΔG below **−0.5 kcal/mol** are labeled **IDEAL CANDIDATE**. All others are labeled **REJECTED**.

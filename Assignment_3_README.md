Notebook 1: Exploratory Data Analysis (EDA)

This notebook performs exploratory data analysis on preprocessed ChEMBL bioactivity data for QSAR modeling.

The workflow includes:

Importing and cleaning bioactivity data

Removing missing values and duplicate SMILES

Converting IC50 (nM) to pIC50 using −log10(IC50 × 10⁻⁹)

Reclassifying compounds as active (pIC50 ≥ 6) or inactive (pIC50 < 6)

Visualizing pIC50 distribution and bioactivity class balance

Generating histograms, bar plots, boxplots, and scatter plots

Performing statistical comparison between active and inactive groups using the Mann–Whitney U test (α = 0.05)

All figures and statistical summaries are exported for reporting.


Notebook 2: Lipinski Descriptor Calculation & Chemical Space Analysis

This notebook calculates Lipinski Rule-of-Five descriptors using RDKit and evaluates their relationship with bioactivity.

Descriptors calculated:

Molecular Weight (MW)

LogP (octanol–water partition coefficient)

Number of Hydrogen Bond Donors

Number of Hydrogen Bond Acceptors

The descriptors are merged with bioactivity data and analyzed using:

Boxplots comparing active vs inactive compounds

Scatter plots (MW vs LogP) for chemical space visualization

Mann–Whitney U test to assess distribution differences

The resulting dataset is saved as df_lipinski.csv for downstream modeling.


Notebook 3: Molecular Fingerprint & Descriptor Generation

This notebook generates molecular fingerprints for QSAR modeling using PaDELPy (PaDEL-Descriptor wrapper).

Steps performed:

Conversion of canonical SMILES to .smi format

Calculation of 881-bit PubChem fingerprints

Calculation of Substructure fingerprints (~307 binary features) using the PaDEL XML configuration

Integration of all fingerprints with bioactivity metadata

Preparation of a machine learning–ready dataset combining PubChem and Substructure fingerprints

The final QSAR dataset is exported as QSAR_dataset.csv.

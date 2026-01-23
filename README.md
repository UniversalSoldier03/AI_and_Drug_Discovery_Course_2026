Assignment Title: QSAR Data Curation Using ChEMBL

Selected target name: Breast cancer type 1 susceptibility protein (BRCA1)

Number of bioactivity records: 21

short description of workflow:

Bioactivity data for Breast cancer type 1 susceptibility protein (BRCA1) were retrieved from the ChEMBL database using the chembl_webresource_client within a Google Colab environment. Google Drive was mounted to enable persistent data storage and file organization across sessions.

The BRCA1 target was identified through a keyword-based search, and the corresponding ChEMBL target identifier (CHEMBL5990) was selected. All reported bioactivity records associated with this target were queried, and entries were restricted to those with IC50 measurements. The resulting dataset was converted into a pandas DataFrame and exported as a raw CSV file for record-keeping.

Data preprocessing involved filtering out entries with missing IC50 values and retaining only records with valid canonical SMILES representations. IC50 values (in nanomolar units) were then used to assign categorical bioactivity labels based on predefined thresholds: compounds with IC50 ≤ 1,000 nM were classified as active, those with IC50 ≥ 10,000 nM as inactive, and values between these thresholds as intermediate.

From the curated dataset, only the relevant fields—molecule ChEMBL ID, canonical SMILES, IC50 standard value, and bioactivity class—were retained to generate a final preprocessed dataset. This cleaned dataset, comprising 21 bioactivity records, was saved as a CSV file and stored in Google Drive for downstream QSAR modeling.

# Protein_Compound_Data_Scraping
Scraping BRENDA for kinetic data related to substrate-enzyme complexes with information on protein sequences, substrate SMILES, and product SMILES


## Data Processing Steps
1. Download all substrate-enzyme catalysis kinetic datasets from BRENDA. We are interested in obtaining enzyme, substrate, and reactant/product data for the aforementioned interactions. 
2. Combine the Km, kcat, and kcat/Km datasets.
3. Identify full reactions from EC numbers and substrate-enzyme names provided by the downloaded BRENDA datasets. This is done using the KEGG EC number to Kegg reaction ID converter, found here: https://rdrr.io/github/ecell/transomics2cytoscape/man/ec2reaction.html
4. Sort through all the reactions and remove any reaction duplicates. 
5. Get list of unique compounds in the dataset and convert compound names to SMILES.
6. Clean up dataset; remove kinetic paraamter value columns. 
7. Get the sequences and active sites for all the UniProt IDs in the dataset and add sequences to dataset.
8. Obtain all PDB IDs and corresponding resolutions for each UniProt ID using the following method: https://stackoverflow.com/questions/37335759/using-python-to-download-specific-pdb-files-from-protein-data-bank
9. Download PDB file for the highest resolution PDB IDs and save in folder. 
10. Search through SwissProt AlphaFold database for missing PDB files in dataset. 
11. Add column to dataset pointing to PDB file location of each datapoint. 
12. Finalize dataset and perform any aesthetic changes. Save to csv.  

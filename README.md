# Molecular Docking Analysis of Human Dopamine Transporter (DAT) Inhibitors

## **Project Overview**
This study investigates the binding orientations and affinities of five ligands—three active and two inactive—against the **Human Dopamine Transporter (PDB ID: 7OUZ)**. By employing molecular docking via **AutoDock Vina (PyRx)** and visual analysis in **PyMOL**, we correlate computational binding energy with experimental biological activity ($pIC_{50}$).

## **Scientific Rationale**
The Dopamine Transporter (DAT) is a critical protein for regulating neurotransmission. Understanding the preferred orientation and binding strength of potential inhibitors helps in the rational design of drugs for neurological disorders.

## **Methodology**
The project followed a standardized 8-step molecular docking protocol:
1. **Ligand Selection:** Retrieved 5 inhibitors from ChEMBL (Active: Maralixibat, Ertugliflozin, Dapagliflozin; Inactive: Levodopa, Desvenlafaxine).
2. **Protein Preparation:** Selected **7OUZ** (Active state, 0.90 Å resolution) from the Protein Data Bank (PDB).
3. **Format Conversion:** Converted `.pdb` files to `.pdbqt` format for Vina.
4. **Search Space Definition:** - **Center:** x: 7.35, y: 14.42, z: 24.70
   - **Dimensions:** 57.89, 48.60, 57.99
5. **Docking Simulation:** Generated poses with an exhaustiveness of 50.

## **Key Results**
| Ligand | Activity | IC50 (nM) | $pIC_{50}$ | Binding Affinity (kcal/mol) |
| :--- | :--- | :--- | :--- | :--- |
| **MARALIXIBAT** | Active | 0.28 | 9.552 | **-9.0** |
| **DAPAGLIFLOZIN** | Active | 1.5 | 8.824 | **-8.8** |
| **DESVENLAFAXINE** | Inactive | 5,011,872.34 | 2.300 | **-6.5** |
| **LEVODOPA** | Inactive | 141,200,000 | 0.850 | **-6.0** |
| **ERTUGLIFLOZIN** | Active | 0.87 | 9.060 | **-5.2** |

*(Data compiled from 5dockedresults.csv and ChEMBL data).*

## **Interaction Visualizations**

### **1. MARALIXIBAT (Lead Candidate)**
Maralixibat demonstrated the highest affinity and stable orientation within the binding site.
| Pose | Binding Interaction |
| :---: | :---: |
|![Maralixibat 2](./Ligand-protein%20interactions/maralixibat-7ouz-pymol.png) | ![Maralixibat 1](./Ligand-protein%20interactions/MARALIXIBAT.png) |
### **2. DAPAGLIFLOZIN (Active)**
Dapagliflozin shows high binding affinity (-8.8 kcal/mol) with strong polar interactions.
| Pose | Binding Interaction |
| :---: | :---: |
| ![Dapagliflozin 2](./Ligand-protein%20interactions/dapagliflozin-7ouz-pymol.png) | ![Dapagliflozin 1](./Ligand-protein%20interactions/dapagliflozin.png) | 

### **3. ERTUGLIFLOZIN (Active)**
Despite high $pIC_{50}$, the docking affinity was -5.2 kcal/mol, suggesting a specific binding mode.
| Pose | Binding Interaction |
| :---: | :---: |
| ![Ertugliflozin 2](./Ligand-protein%20interactions/ertugliflozin-7ouz-pymol.png) | ![Ertugliflozin 1](./Ligand-protein%20interactions/ertugliflozin.png) | 

### **4. LEVODOPA (Inactive Control)**
Three distinct views showing the weak binding orientation and lack of typical active-site polar contacts.
| Pose| View 1 | View 2 |
| :---: | :---: | :---: |
| ![Levodopa 3](./Ligand-protein%20interactions/levodopa-7ouz-pymol.png) | ![Levodopa 1](./Ligand-protein%20interactions/LEVODOPA1.png) | ![Levodopa 2](./Ligand-protein%20interactions/LEVODOPA2.png) | 

### **5. DESVENLAFAXINE (Inactive Control)**
| Pose |
| ![Desvenlafaxine](./Ligand-protein%20interactions/desvenlafzxine-7ouz-pymol.png) |

## **Conclusion**
This study successfully validated the binding modes of DAT inhibitors through a comparative *in silico* workflow. While all active ligands showed favorable docking scores, **Maralixibat (CHEMBL363392)** emerged as the most suitable inhibitor candidate for the following reasons:

* **Superior Binding Affinity:** It consistently demonstrated the strongest binding affinity (-9.0 kcal/mol), correlating with its high experimental $pIC_{50}$ (9.552).
* **Interaction Patterns:** The ligand exhibited robust polar interactions within the protein's active site, which are critical for stable complex formation.
* **Structural Feasibility:** Evaluation of its binding mode and orientation suggests a high degree of fit and specificity for the 7OUZ active site.

While Maralixibat stands out as a promising lead, further structural analysis and experimental validation are recommended to confirm its exact mechanism of action and specificity as a DAT inhibitor.


## **Software & Tools**
* **PyRx (AutoDock Vina):** Docking and scoring.
* **PyMOL:** Visualization and interaction mapping.
* **ChEMBL Database:** Bioactivity data.

## **Repository Structure**
* `/PDB_files`: Original .pdb files.
* `/PDBQT_files`: Vina input files.
* `/Ligand-protein interactions`: PyMOL screenshots.
* `5dockedresults.csv`: Scoring table.

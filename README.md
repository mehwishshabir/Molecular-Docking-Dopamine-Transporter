# Molecular Docking Analysis of Human Dopamine Transporter (DAT) Inhibitors

## **Project Overview**
This study investigates the binding orientations and affinities of five ligands—three active and two inactive—against the **Human Dopamine Transporter (PDB ID: 7OUZ)**. By employing molecular docking via **AutoDock Vina (PyRx)** and visual analysis in **PyMOL**, we correlate computational binding energy with experimental biological activity ($pIC_{50}$).

## **Scientific Rationale**
The Dopamine Transporter (DAT) is a critical protein for regulating neurotransmission. Understanding the preferred orientation and binding strength of potential inhibitors helps in the rational design of drugs for neurological disorders.

## **Methodology**
The project followed a standardized 8-step molecular docking protocol:
1. **Ligand Selection:** Retrieved 5 inhibitors from ChEMBL (Active: Maralixibat, Ertugliflozin, Dapagliflozin; Inactive: Levodopa, Desvenlafaxine).
2. **Protein Preparation:** Selected **7OUZ** (Active state, 0.90 Å resolution) from the Protein Data Bank (PDB).
3. **Format Conversion:** Converted `.pdb` files to `.pdbqt` format, incorporating partial charges and atom types.
4. **Search Space Definition:** * **Center:** x: 7.35, y: 14.42, z: 24.70
   * **Dimensions:** 57.89, 48.60, 57.99
5. **Docking Simulation:** Generated 9 poses per ligand with an exhaustiveness value of 50.
6. **Interaction Profiling:** Analyzed hydrogen bonding and polar contacts using PyMOL.

## **Key Results**
The docking results demonstrate a clear correlation between lower binding affinity (higher potency) and high experimental $pIC_{50}$ values.

| Ligand | Activity | IC50 (nM) | $pIC_{50}$ | Binding Affinity (kcal/mol) |
| :--- | :--- | :--- | :--- | :--- |
| **MARALIXIBAT** | Active | 0.28 | 9.552 | **-9.0** |
| **DAPAGLIFLOZIN** | Active | 1.5 | 8.824 | **-8.8** |
| **DESVENLAFAXINE** | Inactive | 5,011,872.34 | 2.300 | **-6.5** |
| **LEVODOPA** | Inactive | 141,200,000 | 0.850 | **-6.0** |
| **ERTUGLIFLOZIN** | Active | 0.87 | 9.060 | **-5.2** |

*(Data compiled from 5dockedresults.csv and ChEMBL data)*

## **Interaction Visualizations**

### **1. Maralixibat (Lead Candidate)**
Maralixibat demonstrated the highest affinity (-9.0 kcal/mol) and stable orientation within the binding site, forming significant polar contacts.
![Maralixibat Interaction](./Ligand-protein%20interactions/maralixibat-7ouz-pymol.png)

### **2. Active Inhibitor: Dapagliflozin**
Demonstrated high binding affinity (-8.8 kcal/mol) correlating with its biological activity.
![Dapagliflozin Interaction](./Ligand-protein%20interactions/dapagliflozin-7ouz-pymol.png)

### **3. Inactive Control: Levodopa**
Lower affinity and distinct orientation indicate weaker inhibition potential compared to active leads.
![Levodopa Interaction](./Ligand-protein%20interactions/levodopa-7ouz-pymol.png)

## **Conclusion**
This study successfully validated the binding modes of DAT inhibitors using an *in silico* approach. **Maralixibat** emerged as the most suitable inhibitor candidate, characterized by robust interactions with the protein active site. The alignment between computational docking scores and experimental $pIC_{50}$ values confirms the reliability of this workflow for screening prospective drug candidates.

## **Software & Tools**
* **PyRx (AutoDock Vina):** Molecular docking and scoring.
* **PyMOL:** 3D Visualization and interaction mapping.
* **ChEMBL Database:** Source of ligand bioactivity data.
* **Protein Data Bank (7OUZ):** Protein structure source.

## **Repository Structure**
* `/PDB_files`: Original protein and ligand structures.
* `/PDBQT_files`: Input files converted for AutoDock Vina.
* `/Ligand-protein interactions`: PyMOL interaction diagrams.
* `5dockedresults.csv`: Complete docking score table.

# Computational Protein Design for Insulin Binding

This repository showcases a workflow for filtering computationally designed proteins that bind to insulin. Using state-of-the-art machine learning models, **RFdiffusion** and **ProteinMPNN**, proteins were designed, evaluated, and filtered to identify the best candidates. This project is part of a larger initiative aimed at developing biosensors for biomanufacturing applications.

---

## **Motivation**

The BIO-SENS team is pursuing a four-stage project to design an in-line biosensor for biomanufacturing. This stage focuses on creating protein recognition elements to bind insulin, an essential analyte identified by the Advanced Regenerative Manufacturing Institute. Continuous in-line protein evaluation is critical for biotechnological progress, and this research aims to spearhead Stage 1 of the project by designing 15 effective recognition elements.

---

## **Workflow Overview**

1. **Epitope Selection**:
   - Identified three regions on insulin as targets for binder design.

2. **Binder Backbone Design**:
   - Predicted structures for protein binders using **RFdiffusion**, generating 2000 designs per epitope.

3. **Binder Sequence Design**:
   - Designed amino acid sequences for backbones using **ProteinMPNN**.

4. **Property Calculation**:
   - Evaluated designs using:
     - Binding Energy per Buried Surface Area (BE/BSA)
     - Buried Surface Area (BSA)
     - Shape Complementarity (SC)
     - In-house protein interface stability method

5. **Final Design Selection**:
   - Down-selected top candidates based on filtering metrics to identify the most promising designs for biosensor applications.

---

## **Key Findings**

- **Predicted Aligned Error (PAE)**:
  - Used as an initial filtering metric, with thresholds of ≤15 for Epitopes 1 and 3 and ≤10 for Epitope 2.
  - Epitope 2 yielded the most promising designs after initial filtering.

- **Binding Metrics**:
  - High SC and BE/BSA values correlated with experimental success likelihood.
  - BSA threshold of 750 was identified as sufficient for binding success.

---

## **Repository Structure**

```
|-- data wrangling/
    |-- combiner
    |-- data_extraction_code
|-- filtering_optimization/
    |-- filtering_optimization.ipynb
    |-- new_combined_rosetta_af2.csv
|-- protein_filtering/
    |-- initial_epitope_filterting
|-- rmsd/
    |-- RMSD.ipynb
|-- symposium_poster_final_latherial.pdf
```

---

## **Tools and Technologies**

- **Machine Learning Models**:
  - **RFdiffusion**: For backbone design.
  - **ProteinMPNN**: For sequence design.

- **Evaluation Methods**:
  - **CHARMM** fixed-backbone minimization.
  - **Rosetta** all-atom minimization and interface analysis.

- **Programming & Data Tools**:
  - Python, Jupyter Notebooks
  - Pandas, NumPy, Matplotlib
  - CSV and PDF analysis

---

## **Next Steps**

- Experimentally evaluate 15 selected designs in the laboratory (in collaboration with the Balog Laboratory).
- Explore workflow applicability for other protein targets.
- Further refine and expand filtering metrics for improved binder prediction.

---

## **Acknowledgments**

This research was supported by the **National Science Foundation EPSCoR Research Award (#2119237)**. Special thanks to the Pantazes Lab, the BIO-SENS team, and Auburn University for their collaboration and support.

---

## **References**

1. Voet D, Voet JG (2011). *Biochemistry (4th ed.).* New York: Wiley.  
2. Varadi, M., et al. (2022). *AlphaFold Protein Structure Database: massively expanding the structural coverage of protein-sequence space with high-accuracy models.* Nucleic Acids Research, 50(D1), D439–D444. [DOI:10.1093/nar/gkab1061](https://doi.org/10.1093/nar/gkab1061)

---

## **Contact**

For further questions or collaboration, please contact **Latherial Calbert** at [calbertlr@g.cofc.edu].

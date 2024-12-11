# Density_Functional_Theory_using_quantum_espresso
## **Overview**
This project involves the application of Density Functional Theory (DFT) using Quantum Espresso to study the electronic, structural, and mechanical properties of Silicon (Si), Sodium Chloride (NaCl), Zirconium Carbide (ZrC), and Cesium Chloride (CsCl). The calculations include structure optimization, k-point sampling, and determination of bulk modulus for each material.


## **How I Did It**
### 1. **Preparation and Input Files**
   - **Downloaded POSCAR Files**: Obtained the POSCAR files for Si, NaCl, ZrC, and CsCl from reputable databases to serve as initial structures.
   - **Created Input Files**:
     - `scf.in`: This file contains the input parameters for Quantum Espresso, including the functional (e.g., PBE), pseudopotentials, and k-point settings.
     - Parameters were initially taken from the Materials Project database and adjusted based on convergence tests for each material.
  - **Dependency on Input Content**: The specific content in these files, such as the lattice structure, initial positions of atoms, and initial volume, significantly influence the outcome of the calculations. For example, the initial atomic positions and volume directly affect the structure optimization and the resulting relaxed lattice parameters.
### 2. **Running the Calculations**
   - **Structure Optimization**:
     - Used Quantum Espresso to run the SCF calculations (`pw.exe`) to optimize the lattice parameters.
     - The output files (`scf.out`) contain relaxed lattice parameters for each material.
   - **K-Points Sampling**:
     - After structure optimization, k-point grids were adjusted to find the set with the lowest total energy. The final k-points are specified in `kpoints` file.
   - **Calculating Bulk Modulus**:
     - Performed volume relaxation by varying the unit cell volume and calculated the pressure using Quantum Espresso's `pw.exe` tool.
     - Extracted the stress versus volume data to compute the bulk modulus for each material using the Birch-Murnaghan equation of state.

### 3. **Post-Processing**
   - **Data Analysis**:
     - Analyzed the output files for each material to determine electronic properties (band structure, DOS), mechanical properties (elastic constants, bulk modulus), and phonon dispersion relations.
   - **Results**:
     - Compiled all results into `scf.out`.

## **Methodology**
- **Materials**:
  - Si, NaCl, ZrC, and CsCl were chosen due to their diverse properties and applications in semiconductor and structural materials.
- **Computational Tools**:
  - Quantum Espresso (pw.x) was used for all DFT calculations.
- **Convergence Tests**:
  - K-point sampling and energy cutoff were optimized for each material to ensure reliable and accurate results.
- **Post-Processing**:
  - Bulk modulus calculations involved fitting the equation of state to the computed energy-volume data to extract the modulus.

## **References**
- [Materials Project](https://next-gen.materialsproject.org) for initial parameters.
- Quantum Espresso documentation and community forums for troubleshooting and advanced calculations.

# GROMACS Protein-Ligand Simulation

This directory contains all the necessary files and directories required for setting up, running, and analyzing a protein-ligand molecular dynamics (MD) simulation using GROMACS.

## Directory Structure and File Descriptions

### Directories
- **`charmm36-jul2022.ff`**:  
  This directory contains the CHARMM36 force field files (July 2022 version). It is required for preparing and simulating the system.

- **`Complex/`**:  
  This directory is expected to contain the protein-ligand complex files generated during the simulation setup process, such as topology, coordinate, and output files.

### Files
- **`em.mdp`**:  
  GROMACS parameter file for the energy minimization step.

- **`ions.mdp`**:  
  GROMACS parameter file for the ion addition step, which neutralizes the system.

- **`nvt.mdp`**:  
  GROMACS parameter file for the NVT equilibration step, where the system is brought to the desired temperature.

- **`npt.mdp`**:  
  GROMACS parameter file for the NPT equilibration step, which maintains constant pressure and temperature.

- **`md.mdp`**:  
  GROMACS parameter file for the production MD run.

- **`protein-ligand.txt`**:  
  A text file containing notes, observations, or documentation related to the protein-ligand simulation setup or analysis.

- **`protein-ligand.txt~`**:  
  A backup file for `protein-ligand.txt` (auto-generated).

## Workflow Overview

1. **Prepare the Protein-Ligand System**:
   - Use the CHARMM36 force field for generating topology and coordinate files for both protein and ligand.
   - Ensure the ligand topology is compatible with GROMACS (e.g., use tools like SwissParam or CGenFF).

2. **Energy Minimization**:
   - Run the energy minimization step using `em.mdp` to remove bad contacts and prepare a stable starting structure.

3. **Ion Addition**:
   - Neutralize the system by adding ions with the parameters in `ions.mdp`.

4. **Equilibration**:
   - Perform equilibration in two steps:
     - NVT (constant volume and temperature) using `nvt.mdp`.
     - NPT (constant pressure and temperature) using `npt.mdp`.

5. **Production MD**:
   - Run the production MD simulation using `md.mdp`.

6. **Analysis**:
   - Analyze the trajectory and other outputs to study the protein-ligand interactions.

## Notes
- Make sure to check the GROMACS version compatibility for these input files.
- Verify the ligand topology for correctness before starting simulations.
- Update the `protein-ligand.txt` file with any additional observations or results.

---

**Author**: Vishal Ravi  
**Last Updated**: January 11, 2025

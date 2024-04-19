This is the input file to calculate MMGBSA and MMPBSA for protein ligand complexes

----Activate the conda environment with gmxMMPBSA installed-----

conda activate gmxMMPBSA

----Use MPI to run the MMGBSA/MMPBSA calculations--------

mpirun -oversubscribe -np 16 gmx_MMPBSA -O -i mmpbsa.in -cs md_0_200.tpr -ct md_0_200.xtc -ci index.ndx -cg 1 13 -cp topol.top -o FINAL_RESULTS_MMPBSA.dat -eo FINAL_RESULTS_MMPBSA.csv -do FINAL_DECOMP_MMPBSA.dat -deo FINAL_DECOMP_MMPBSA.csv

----To reanalize the graphs after running the calculation------

gmx_MMPBSA_ana -f _GMXMMPBSA_info

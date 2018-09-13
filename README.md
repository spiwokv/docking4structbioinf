# Docking and virtual screening tutorial for Structural bioinformatics

This tutorial is inspired by the article of Chris de Graaf and co-workers [1]. Histamine is an
important biogenic amine (decarboxylation product of histidine) involved in allergy. Antagonists
and inverse agonists of the histamine receptor can be used as antihistaminics to treat allergy.
Relatively recently solved 3D structure of this receptor [2] makes it possible to discover new
antihistaminics by structure-based drug design. In the article of Chris de Graaf and co-workers,
authors virtually screened 108790 compounds. They selected, purchased and tested 26 of them, 19
turned out to be active with K_D < 10 microM. We can try a simplified version of this virtual
screening.

The authors took 108790 compounds and removed compounds that were too big. This resulted to 95
147 compounds. These compounds were docked into the binding site of Histamine 1 receptor
and the authors also calculated “interaction fingerprints” (in this tutorial we will use only docking).
Based on charge of the molecule, docking scores and fingerprints they selected 611 compounds.
After further filtering and visual inspection they selected 26 compounds. These compounds were
purchased and tested experimentally. Out of them, 19 showed strong binding to histamine 1 receptor.

In a simplified virtual screening procedure we will dock 21 compounds identified and
experimentally confirmed in Ref. 1 as ligands of histamine 1 receptor. Then we will download
another set of compounds randomly picked from ZINC database [3], we will dock them and
compare them with known ligands. Finally we will evaluate the virtual screening procedure in terms
of its ability to distinguish between ligands and inactive molecules.

Program PLANTS (Protein-Ligand ANT System) [4] is used for docking. It uses an algorithm
called ant colony optimization, which is inspired by behaviour of real ants when they are trying to
find the shortest path between food and ant nest. This program can be obtained under academic
license from the web site of its developers.

Go to the PDB web site and find the structure of histamine 1 receptor in the complex with
Doxepin [2]. Download the PDB file and make its copy. Open the copy in UCSF Chimera and
remove all non-protein atoms. Then add hydrogen atoms. Use options "considering H-bonds" for
protonation and "determined by the method" for His protonation. Then save the file in mol2
formate. Addition of charges is not necessary.

Go back to original PDB file and view its text. Find the HETATM lines corresponding to the
Doxepin and find its atom C6. This atom is approximately in the centre of the ligand and its
coordinates can be used to define the centre of the binding site. Write down its Cartesian
coordinates.

Take structures of known ligands from the articles. They could be supplied to you either as
individual *mol2* files or a single *mol2* file. Place a ligand *mol2* file, receptor *mol2*
gile and PLANTS executable to a separate directory. Then copy there a configuration file
from PLANTS example session. 


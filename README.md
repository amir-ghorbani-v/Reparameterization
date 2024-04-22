#################################################################################
Copyright 2024, Amir Ghorbani
#################################################################################
This file is part of:
The effect of electron-phonon coupling on cascade-induced damage production in Zirconium

This is a free software: you can redistribute it and/or modify it under the terms of the GNU General Public License version 3 (GPLv3) as published by the Free Software Foundation.

This project is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this project. If not, see https://www.gnu.org/licenses/.

When using this code, please cite the following paper:
Ghorbani, A., Luo, Y., Saidi, P. and Béland, L.K., 2024. Anisotropic diffusion of radiation-induced self-interstitial clusters in HCP zirconium: A molecular dynamics and rate-theory assessment. Scripta Materialia, 238, p.115755.
DOI: 10.1016/j.scriptamat.2023.115755

#################################################################################
Introduction
#################################################################################
This is a reparameterization algorithm that minimizes the cost function between EAM and DFT measurements.
The case studied here, M3, is Mendelev and Ackland’s Zr potential (#3) which best describes the phase transformation.

#################################################################################
How it works
#################################################################################
This reparameterization has six steps and benchmarks against DFT measurements in two modes,
namely: equation of state (EOS) and embedded dimer Along A (ED-A), C (ED-C) and (AC (ED-
AC) directions. During this process, the electron density (ρ), pair part (V ) and embedding part (F )
functions of EAM potentials. First, effective gauge transformation (EGT) is performed us-
ing Pasiano et al. method. Second, the ρ is gradually saturated at ρ = 1. Third, the V is trans-
formed into Ziegler-Biersack-Littmark (ZBL) model at close atomic distances over the transition region
of 2 to 2.5  ̊A, enabling close atomic interactions. Fourth, V is minimized to DFT results from 1.25
to 2.5  ̊A using DFT embedded dimer results. Fifth, F is extrapolated twice over ρ to cover close atomic
distances. Sixth, EOS is used to minimize the deviation from DFT by altering F over ρ values of
3.2 to 6, considering regions for smooth transitions. Figure 1-a, b and c show ρ, V and F functions before
and after reparam eterization in blue and red, respectively. It shows the EOS calculations using both potentials in
comparison with DFT measurements. It also shows ED calculations in comparison with DFT measurements along
A, C and AC directions.

##################################################################################
COMPILE
##################################################################################

This project uses LAMMPS to calculate EAM measurements. Compile LAMMPS im Python. Check: https://docs.lammps.org/Python_head.html

<img align="right" width=15% src="logo.gif" />

[comment]: <![](./title.svg)>
# 2qubits

![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)
![License](https://img.shields.io/github/license/diegoscantam/2qubits)
![Size](https://img.shields.io/github/repo-size/diegoscantam/2qubits)

:warning: This repository is a work in progress in constant development! :hammer_and_wrench:

## About
Implementation of a Python simulation of a quantum system of a few qubits. A variational estimate of the ground state energy of the deuteron is simulated on a Qiskit quantum circuit. This is done in two different ways, one being the representation of each quantum harmonic oscillator state the nucleus can occupy as a qubit, the other being the relative mixing between singlet and triplet spin and isospin states of the system mapped into a quantum circuit. Secondly, some quantum correction algorithms are implemented.

The present work is done in collaboration with [TIFPA (Trento Institute for Fundamental Physics and Applications)](https://www.tifpa.infn.it/) research centre and the [University of Trento](https://www.unitn.it/en) as part of a quantum computing internship.

## Deuteron: the deuterium nucleus
The deuteron is the bound state of a proton and a neutron. In order to estimate the binding energy of the system, there are two main approaches one could follow involving a simulation on a quantum computer.

### EFT Hamiltonian
The first being the one mapping the creation and destruction operators of the deuteron into combinations of Pauli gates. The ladder operators $a_n^\dagger$ and $a_n$ create and annihilate a deuteron in the harmonic oscillator state $|n \rangle$. The Hamiltonian (from pionless effective field theory) is of the form

$$
H_N = \sum_{n,n'=0}^{N-1} \langle n' | T+V | n \rangle \\,a_{n'}^\dagger a_n.
$$

Thanks to the Jordan-Wigner transformation, the Hamiltonian is expressed in terms of Pauli matrices, allowing us to map it into a quantum circuit with $N$ qubits. By calculating the variational ground state energies for $H_1$, $H_2$ and $H_3$, one can extrapolate the infinite-basis binding energy using the harmonic oscillator variant of Lüscher formula.

### Relative mixing between $^3 S_1$ and $^3 D_1$ partial waves
The second being the study of the relative mixing between the only two allowed states for the ground state deuteron: a isospin singlet, spin triplet state with $L=0$ ($^3 S_1$) and $L=2$ ($^3 D_1$). One can consider the two-level system built from the $S$ wave $\ket{\phi_S}$ and $D$ wave $\ket{\phi_D}$ such that the Hamiltonian is of the form:

$$
H = \left(\begin{matrix} 
    \braket{\phi_S|H|\phi_S} & \braket{\phi_S|H|\phi_D} \\ 
    \braket{\phi_D|H|\phi_S} & \braket{\phi_D|H|\phi_D}\end{matrix}\right).
$$

By introducing the relative mixing parameter $\xi$, one can calculate the optimal mixing between the two partial waves in order to obtain the lowest energy:

$$
\ket{\psi} = \sqrt{\xi} \\, \ket{\phi_S} + \sqrt{1-\xi} \\, \ket{\phi_D}.
$$

## Results
Here you can find an example of some results obtained with the code in `deuteron.ipynb`:

<p align="center">
    <img width=33% src="plots/E_2.png"> 
&nbsp; &nbsp; &nbsp; &nbsp;
    <img width=33% src="plots/E_3.png"> 
&nbsp; &nbsp; &nbsp; &nbsp;
    <img width=33% src="plots/fit_luscher.png"> 
&nbsp; &nbsp; &nbsp; &nbsp;
    <img width=33% src="plots/mixing.png"> 
</p>

## License

The code here presented is released under version 3 of the [GNU General Public License](https://www.gnu.org/licenses/gpl-3.0.html).

# 2qubits

![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)
![License](https://img.shields.io/github/license/diegoscantam/2qubits)
![Size](https://img.shields.io/github/repo-size/diegoscantam/2qubits)

:warning: This repository is a work in progress in constant development! :hammer_and_wrench:

## About
Implementation of a Python simulation of a quantum system of a few qubits. A variational estimate of the ground state energy of the deuteron is simulated on a Qiskit quantum circuit. This is done in two different ways, one being the representation of each quantum harmonic oscillator state the nucleus can occupy as a qubit, the other being the relative mixing between singlet and triplet spin states of the system mapped into a two qubits circuit. Secondly, some quantum correction algorithms are implemented.

The present work is done in collaboration with [TIFPA (Trento Institute for Fundamental Physics and Applications)](https://www.tifpa.infn.it/) research centre as part of a quantum computing internship.

## Deuteron: the deuterium nucleus
The deuteron is the bound state of a proton and a neutron. In order to estimate the binding energy of the system, there are two main approaches one could follow involving a simulation on a quantum computer.

The first being the one mapping the creation and destruction operators of the deuteron into combinations of Pauli gates. The ladder operators $a_n^\dagger$ and $a_n$ create and annihilate a deuteron in the harmonic oscillator state $|n \rangle$. The Hamiltonian is of the form

$$
H_N = \sum_{n,n'=0}^{N-1} \langle n' | T+V | n \rangle a_{n'}^\dagger a_n.
$$

Thanks to the Jordan-Wigner transformation, the Hamiltonian is expressed in terms of Pauli matrices, allowing us to map it into a quantum circuit with $N$ qubits. By calculating the variational ground state energies for $H_1$, $H_2$ and $H_3$, one can extrapolate the infinite-basis binding energy using the harmonic oscillator variant of Lüscher formula.

## License

The code here presented is released under version 3 of the [GNU General Public License](https://www.gnu.org/licenses/gpl-3.0.html).

## Aknowledgements
<button style="border: transparent; background-color: transparent;">
    <img align="left" width=10% src="https://avatars.githubusercontent.com/u/112166702?v="> 
</button>

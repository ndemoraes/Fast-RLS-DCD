# Fast-RLS-DCD
This repository contains the implementations of the Fast RLS-DCD adaptive filtering algorithm described in the conference paper "A faster RLS-DCD adaptive filtering algorithm", presented at the 19th International Symposium on Wireless Communications Systems July 14-17, 2024, Rio de Janeiro, Brazil https://iswcs2024.usuarios.rdc.puc-rio.br/

Authors
Naomi J. Sutcliffe de Moraes
Institute of Mathematics and Statisics, U. of São Paulo, Brazil

Vítor H. Nascimento
Escola Politécnica, U. of São Paulo, Brazil

Daniel C. Vidal
Escola Politécnica, U. of São Paulo, Brazil

Carlos A. Prete Jr.
Escola Politécnica, U. of São Paulo, Brazil

Yuriy V. Zakharov
U. of York, UK

Abstract
The RLS and RLS-DCD algorithms are commonly used for adaptive filtering applications due to their fast convergence even under correlated inputs.  RLS-DCD is a numerically robust and easy to implement version of RLS, but although it requires only BigO(M) arithmetic operations, the total number of operations in a naive implementation is BigO(M^2) due to copy operations when the autocorrelation matrix is updated. The novel data structure and algorithm described in this paper reduce the number of copy operations to BigO(M) and cut the amount of memory needed to about half, speeding up implementations of RLS-DCD significantly for large values of $M$.

In order to capitalize on the special form of the update equation, we store the matrix along its diagonals in what we call the Diagonal Circular-Buffer (DCB) Format. We use a jagged array structure in which each element is a circular buffer representing one diagonal of the original matrix.

We implemented the data structure and algorithm in C, Julia, Python and MATLAB, and show that the fast RLS-DCD algorithm (which uses the DCB data structure) is faster than the RLS or RLS-DCD algorithms in almost all cases, particularly for large M.  This algorithm can be used for any adaptive filtering application where RLS-DCD would be used by simply altering the data structure and related matrix and vector update functions. The benefits of increased speed and reduced memory use would be significant for larger systems.

The code for the C language implementation is in this repository:
https://github.com/ndemoraes/Fast-RLS-DCD-C-language

The code for the Julia language implementation is in this repository:
https://github.com/ndemoraes/Fast-RLS-DCD-Julia

The code for the Python implementations (interpreted and compiled) are in this repository:
https://github.com/ndemoraes/Fast-RLS-DCD-Python

The code for the MATLAB implementation is in this repository:
https://github.com/ndemoraes/Fast-RLS-DCD-MATLAB

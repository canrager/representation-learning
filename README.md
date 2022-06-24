# Learning Quantum State Representations


Neural networks reconstruct a quantum state from measurements. I use a supervised and an unsupervised approach (as shown below). 

![ae_graphic](https://user-images.githubusercontent.com/61095597/175553056-1a360cee-b6b5-4462-9155-a44d79daddf2.png)

_An Encoder_ $E$
_maps the measurement probabilities_ $\mathbf{p}$
_to a lower dimensional representation_ $\ell$
. 
_If the decoder_ $D$
_successfully reconstructs the probabilities_
$\tilde{\mathbf{p}} \approx \mathbf{p}$
, $\ell$
_holds all necessary information of the measured state and is thus a valid state representation. State reconstruction for a single qubit system with three degrees of freedom is shown._

## Dataset Generation

Single and two qubit systems are considered.
One datapoint 
($\rho$, $\mathbf{p}$)
consists of a mixed quantum state 
$\rho$ 
and its measurement probabilities 
$\mathbf{p}$
for a set of projective valued measurements (PVMs) called
$\hat{P_i}$.
Here, 
$p_i = \mathrm{Tr}(\rho \hat{P_i})$
is the probability of measuring state 
$\rho$ 
along the projector 
$\hat{P_i}$
.
All states in a dataset are measured with the same set of PVMs.
I sample mixed quantum states and a sets of PVMs from a uniform distribution. 

## Supervised State Reconstruction

In the supervised approach a feedforward network reconstructs a given state representation
$\rho$
from measurement data 
$\mathbf{p}$
. This model can reconstruct unseen 
$\rho$
measured with the same set of PVMs used in the training dataset.
A system of $N$
qubits has $4N-1$
degrees of freedom.
I see that measurements with $4N-1$ random PVMs are sufficient for state reconstruction, as expected for linear independent measurements.


## Unsupervised State Reconstruction

An encoder maps the measurement data 
$\mathbf{p}$
to a latent layer 
$\mathbf{l}$ 
with 
$\mathrm{dim} \mathbf{l} \le \mathrm{dim} \mathbf{p}$
. 
From the latent representation
$\mathbf{l}$ 
a decoder reconstructs the measurement data 
$\mathbf{p}$ .
As expected, the reconstruction error for significantly after for 
$\mathrm{dim} \mathbf{l} \le 4N -1$. 
We further tune single parameters of the quantum state rho and observe mostly linear behavior.

*Bachelor's degree in physics at the University of Innsbruck\
Supervised by Prof. Dr. Hans J. Briegel and Hendrik Poulsen Nautrup, PhD*

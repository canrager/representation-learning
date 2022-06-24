# Learning Qubit Representations


Neural networks reconstruct a quantum state from measurements. I use a supervised approach (feed forward network) and an unsupervised approach (autoencoder). Single and two qubit systems are considered.

![ae_graphic](https://user-images.githubusercontent.com/61095597/175542694-52c8b2b4-9c93-4233-99b6-99a6b82e32b4.png)



## Dataset Generation

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

In the supervised approach a feedforward network reconstructs a given state representation from measurement data p. This model can reconstruct unseen rho measured with the same set of PVMs used in the training dataset.


## Unsupervised State Reconstruction

An encoder maps the measurement data 
$\mathbf{p}$
to a latent layer 
$\mathbf{l}$ 
with 
$\mathrm{dim} \mathbf{l} \l \mathrm{dim} \mathbf{p}. 
From the latent representation
$\mathbf{l}$ 
a decoder reconstructs the measurement data 
$\mathbf{p}$ .

As a system of $N$
qubits has $4N-1$
degrees of freedom, we expect the reconstruction error to rise significantly after for \mathrm{dim} \mathbf{l}
smaller $4N -1$. 
This is supported by the experiment.

We further tune single parameters of the quantum state rho and observe mostly linear behavior. Nonlinear behavior is oberved in 2/9 cases.

*Bachelor's degree in physics at the University of Innsbruck.\
Supervised by Prof. Dr. Hans J. Briegel and Hendrik Poulsen Nautrup, PhD*

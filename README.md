# Learning State Representation for Quantum Systems



Neural networks reconstruct the quantum state from measurements. I use a supervised approach (feed forward network) and an unsupervised approach (autoencoder). Single and two qubit systems are considered.

## Dataset generation
One datapoint 
($\rho$, $\mathbf{p}$)
consists of a mixed quantum state 
$\rho$ 
and its measurement probabilities 
$\mathbf{p}$
for a set of projective valued measurements 
{
$\hat{P_i}$
}
${}_i$
(PVMs).
Here, 
$p_i = \mathrm{Tr}(\rho \hat{P_i})$
is the probability of measuring state $\rho$ along the projector ${\hat{P_i}$.

Across a dataset multiple states are measured with the same set of PVMs.
I sample mixed quantum states and a sets of projective valued measurements (PVMs) from a uniform distribution. $\mathbf{p}$ is a vector contanining the probabilities of measuring a quantum state $\rho$ with a set of PVMs P . 

## Supervised State Reconstruction

## Unsupervised State Reconstruction

Thesis of bachelor's degree in physics at the university of Innsbruck.
Supervised by 

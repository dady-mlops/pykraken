# PyKraken
Python implementation of normal mode solver for underwater acoustic propagation. This implementation is developed by
_Hunter Akins_ from _Scripps Institution of Oceanography, UC San Diego_. I use this code for KRAKEN understanding.

<p align="center">
  <img src="https://github.com/dady-mlops/pykraken/blob/main/KRAKEN.gif" alt="KRAKEN logo"/>
</p>

More or less a translation of Michael Porter's KRAKEN.
Some small differences:
- I continue to do bisection and Brent for all meshes instead of switching to secant method with deflation
- I do not have partial pivoting in my inverse iteration tridiagonal solver (at this point)

A big difference:
- Elastic layers are not supported

File list:
- <code>pynm_env.py</code> The Env object used to manage all of the environmental parameters and to run the forward model, save results
- <code>sturm_seq.py</code> The numerical code for solving the sturm seq eigenvalue problem
- <code>mesh_routines.py</code> Code for creating meshes
- <code>shooting_routines.py</code> Shooting through layers
- <code>inverse_iterations.py</code> Solving for eigenvectors from eigenvalues
- <code>pressure_calc.py</code> Some helper functions for computing pressure fields using the modal sum
- <code>group_pert.py</code> Calculating modal group speed from perturbation theory
- <code>attn_pert.py</code> Calculating attenuation values using perturbation theory
- <code>coupled_modes.py</code> Coupled mode field calc (in work)
- <code>env_pert.py</code> PertEnv object, inherits Env. Adds some extra methods for managing making changes to the Env using parameterizations. Also computes first order corrections to wavenumbers using perturbation theory
- <code>misc.py</code> Some numerical integrations
- <code>pekeris_test.py</code> compare with KRAKEN (not tracked by git)
- <code>pekeris_comp.py</code> compare with KRAKEN (not tracked by git)



# Numerical attenuated Radon transform stability estimates
for
### SINGULAR STABILITY ESTIMATES FOR PASSIVE GAMMA EMISSION TOMOGRAPHY OF SPENT NUCLEAR FUEL (2026)
by T. Heikkilä, T. Helin, S. Holman, S. R. Jathar and J. Railo

Single ray stability estimates for different simple tangencies and perturbed rod values. 
The phantom is defined by disc centers and radii, and the pencil-beam data are computed in closed form: along a line the
coefficients are piecewise constant, so $R_a f$ is an exact sum over rod chords.

### Conventions 

- Lengths in mm, attenuation in 1/mm, angles in rad.

- Geometry and values are *almost* realistic.

- $\Omega = B(0, r_\mathrm{out})$ with moderator attenuation $a_0$ and no emission; rods $B_q = B(c_q, r)$ with constant $(a_q, f_q)$.
- The detector location $x(\psi) \in \partial\Omega$ is fixed and $\theta(\omega) = (\cos\omega, \sin\omega)$ is the ray direction towards the detector, so the *attenuated Radon transform* can be written as
  $$H(\omega) = R_a f\big(x(\psi), \theta(\omega)\big) = \int_0^\infty f\big(x(\psi) - s\theta(\omega)\big)\exp\Big(-\int_0^s a\big(x(\psi) - \sigma\theta(\omega)\big)\, d\sigma\Big)\, ds,$$
  i.e. with the backward ray from the detector.

### Experiments

- Numerically estimate angular derivatives in $\Phi_D[H]$ and $\Phi_N[H]$, where $H = R_a f - R_{\tilde a} \tilde f$. The input pair $(\tilde a, \tilde f)$ is different from a fixed reference pair $(a,f)$ only at a single rod $B_p$ by
    - <span style="color:#1f77b4;">Emission is 20% lower:</span> $\tilde f_p = 0.8 f_p$.
    - <span style="color:#ff7f0e;">Attenuation is 50% higher:</span> $\tilde a_p = 1.5 a_p$.
    - <span style="color:#2ca02c;">Emission is 20% lower and attenuation is 50% higher:</span> $\tilde f_p = 0.8 f_p, \tilde a_p = 1.5 a_p$.
- The ray is tangent to the rod $B_p$ and  
    (i) meets no other rods  
    (ii) passes through a second rod  
<img src="images/ray_setup_i.png" alt="Ray (i) which is tangent to just one rod" width=360px>
<img src="images/ray_setup_ii.png" alt="Ray (ii) which goes through a second rod" width=360px>

- For comparison the true limit values are computed since the phantom and geometry are known.
<img src="images/analytic_estimates_i.png" alt="Estimates for case (i)" width=720px>

- From the numerical limits, the emission and attenuation values $\tilde f$ and $\tilde a$ are recovered via extrapolation at the tangency. These values are compared to the true values.
    - There is no noise in the data and we only consider recovery of a single rod.

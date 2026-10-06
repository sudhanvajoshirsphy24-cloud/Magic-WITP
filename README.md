# Magic-WITP: data for Fig. 2

Data for the article *Stabilizer and Haar scramblers yield equal mean fidelity but unequal fluctuations in black-hole-inspired teleportation*, by Sudhanva Joshi and Sunil Kumar Mishra, Department of Physics, IIT (BHU) Varanasi. Preprint: arXiv:2606.19180 (version 3).

This repository contains the numerical data plotted in Fig. 2. Every curve in Figs. 2(a) and 2(b) also follows from the closed-form expressions in the article, so the files below let readers re-plot the figure and check the quoted numbers without running any simulation.

## Conventions

These follow Sec. II of the article.

- Each side, `L` and `R`, has `n` qubits, prepared in the maximally entangled state (infinite temperature).
- The message is inserted into the first qubit of `L` by a SWAP, the sides are coupled by the size coupling of strength `g`, and the decoder on `R` is `U^T`.
- `F` is the overlap of the reference qubit and the first qubit of `R` with the singlet state, Eq. (4) of the article. Its no-transfer value is 1/4.
- `gamma = g n`.
- Clifford scramblers are uniformly random `n`-qubit Clifford unitaries. Haar scramblers come from a QR decomposition with the Mezzadri phase correction.
- `M2` is the stabilizer Renyi entropy, base 2, in bits.

## Files

| File | Figure | Contents |
|---|---|---|
| `fig2a_fidelity_samples_clifford_n4.csv` | 2(a) | Raw fidelities at `n = 4`. Each of the 1000 rows is one independent Clifford scrambler; the 9 columns are `gamma` = 0.8, 1.6, 2.4, 3.2, 4.0, 4.8, 5.6, 7.0, 9.0. |
| `fig2a_fidelity_samples_haar_n4.csv` | 2(a) | The same for 1000 Haar scramblers. |
| `fig2a_summary_n4.csv` | 2(a) | The plotted points: mean of `F` and its standard error (population standard deviation divided by the square root of 1000) for each ensemble. |
| `fig2b_std_F_haar.csv` | 2(b), squares | At `gamma = 4 pi/3`: number of Haar scramblers, sample standard deviation of `F` (ddof = 1), and its error from 300 bootstrap resamples, for `n` = 2 to 8. |
| `fig2b_exact_curves.csv` | 2(b), lines | At `g = 4 pi/(3n)`: exact mean infidelity `1 - <F>` (Eq. (9)) and exact standard deviation of `F` over Clifford scramblers (Proposition 2), for `n` from 2 to 2000. |
| `fig2c_doped_clifford_n3.csv` | 2(c) | At `n = 3` and `g = 1.095`, with 1500 scramblers per row: doped Clifford circuits with `t` T gates (Eq. (6), each T on a uniformly chosen qubit), plus a Haar reference row. Columns: mean, standard error and standard deviation of `F`; mean and standard error of `M2` of the scrambled state `U I U^dagger |Psi_0>` on all 8 qubits, before the coupling. |
| `fig2_data.npz` | all | The same arrays in one NumPy archive, with keys prefixed `fig2a_`, `fig2b_` and `fig2c_`. |

Standard errors in `fig2a_*` and `fig2c_*` use the population standard deviation (ddof = 0).

## Not included

The simulation code, and the data behind the remaining numerical checks quoted in the text (Secs. VI and VII and Appendix B), are available from the authors upon reasonable request.

## Citation

If you use these data, please cite the article and this dataset from arXiv:2606.19180.

## License

CC BY 4.0

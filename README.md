# Both prime-race moves finish by a factor of 10¹⁸

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24412095.svg)](https://doi.org/10.5281/zenodo.24412095)

This result is now maintained in [theta-host-split-inert-race](https://github.com/leecrossley/theta-host-split-inert-race/tree/main/results/theta-race-filtered-deadline). This repository is archived and keeps its releases and DOI.

**For every real starting height $`H\ge1`$, the dyadic 547/727 prime-ideal race has both a gain and a loss exceeding $`1.9735\log2`$ in magnitude by $`10^{18}H`$.** Both moves begin strictly after $`H`$. The gain and the loss may start at different heights. The previous universal factor was $`e^{175}`$, about $`10^{76}`$. [Theorem and proof](PROOF.md) · [Earlier upper bound](https://github.com/leecrossley/theta-race-fixed-factor/blob/12b7c94cfb9586c25fb29e7c7aaf0a20adaf5b2f/PROOF.md)

| Part of the proof | Certificate |
|---|---|
| $`1\le H\le10^9`$ | An existing direct prime count gives both moves by $`18H`$. [Finite theorem](https://github.com/leecrossley/theta-race-factor-18/blob/31ea5d495ca29f7f17869d1a3f321000266e4867/PROOF.md) |
| $`10^9\lt H\lt e^{100}`$ | Six fixed abscissae certify three pairs of moves with normalized magnitudes greater than 20. [Height checks](filter_bound.py) |
| $`H\ge e^{100}`$ | A compact nonnegative average isolates one zero. Its contribution exceeds the sum of the other terms by enough to force both signs in every allowed window. [Filter weights](evidence/filter.json) |

Two independent Poisson calculations certify that all zeros through ordinate 48 occur in the signed bracket table. Two different evaluations of the filter bound the contribution of the full spectrum. The gap between the lower obstruction $`2e^6=806.857586\ldots`$ and the upper factor remains open. [Lower bound](https://github.com/leecrossley/theta-race-factor-400/blob/f1773b07a55e76947d4e0c6ab19a112fd91fe6cf/PROOF.md) · [Prior work](PRIOR-WORK.md) · [Verification transcript](evidence/check.txt)

## Replay

In a Python 3.10+ virtual environment run

```sh
python -m pip install -r requirements.txt
python check_spectrum.py
python filter_bound.py
python independent.py
python check_source.py
```

On x86-64 Linux with Git, curl, tar and zstd, `bash verify-release.sh` checks the file hashes, upstream statement and verification records, the numerical certificates and five local Lean deductions. With Lean 4.33.1 on PATH and a built Git checkout of Mathlib at commit `0df444a360eaa60ab8c11dca51a86af692955474` with no local changes, run `bash verify-release.sh /path/to/mathlib4`. An optional second argument gives a local directory containing the five upstream records. The Fourier arguments and explicit formula are written proofs. [Local Lean file](FilteredDeadline.lean) · [File hashes](SHA256SUMS) · [Hardy-sign replay for the bracket table](https://github.com/leecrossley/theta-race-factor-400/releases/tag/v1.0.0)

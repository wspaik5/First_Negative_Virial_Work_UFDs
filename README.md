# First numerical demonstration of negative density-weighted virial work in three ultra-faint dwarfs

This repository accompanies the independent technical note

> **First numerical demonstration of negative density-weighted virial work in three ultra-faint dwarfs under an unregistered Hessian-augmented field law**  
> (Won Shik Paik, October 2026)

which records the first numerical demonstration, within the UDCT series, of strongly negative density-weighted virial work for Leo IV, Pegasus III and Hydrus I under one unregistered Hessian-augmented field law. The script reproduces the conditional local-field model calculations. It is not an observational detection, not a rerun of any historical preregistered proxy, and not a result for standard AQUAL or QUMOND.

- This note (GitHub): https://github.com/wspaik5/Negative_Virial_Work_Three_UFDs  
- This note (Zenodo): [DOI to be assigned upon deposit]  
- Original consolidated record (UDCT v7.06): https://doi.org/10.5281/zenodo.23039754 · https://github.com/wspaik5/UDCT_v7.06_Hessian_Term_Sign_Audit

Script file: `reproduce_negative_virial_work.py`

## Install and run

Use Python 3.10+ with NumPy and SciPy:

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install "numpy>=1.24" "scipy>=1.10"

# Fast first check (recommended)
python reproduce_negative_virial_work.py --smoke --mode baseline > baseline.json
```

Run `python reproduce_negative_virial_work.py --help` for all switches. Start with `--smoke` or one object at a time.

## Smoke-test expected values

Rows are Leo IV, Pegasus III, Hydrus I; each entry is Plummer / tapered cusp.

| Diagnostic | Expected smoke / paper value |
| --- | --- |
| Baseline \(V/V_N\) | −683.84 / −969.06 ; −810.90 / −1489.62 ; −415.42 / −299.67 |
| Joint \(\alpha\) crossing of \(E\) and \(H\) | 0.01903 / 0.06425 ; 0.02426 / 0.10556 ; 0.00320 / 0.00520 |

A third party can confirm a working checkout with:

```bash
python reproduce_negative_virial_work.py --smoke --mode baseline --object "Hydrus I"
```

and looking for Plummer `"virial":` near `-415.42`.

## Scope

The negative density-weighted virial work arises because the action-derived Hessian contribution exceeds the positive leading term in this specific unregistered candidate. Standard MOND-family field equations do not contain the extra tensor under audit. The calculation uses a local second-order Taylor environment and idealized profiles; it is not a full self-consistent three-dimensional equilibrium.

For the full narrative, limits, and selected prior UDCT records, see the accompanying PDF note.

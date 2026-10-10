# Reconstructed jet mass distributions for hadronic top-quark production

Dylan Zhang and Jake Breckenridge — San Diego Supercomputer Center Mentor Assistance Program, UC San Diego.

This project reconstructs W-boson and top-quark candidates from simulated jet data and compares Gaussian and Lorentzian mass fits using chi-squared. The poster reports a lower Lorentzian chi-squared for three of four distributions; the second top-candidate distribution favors the Gaussian in that reported setup.

## Research question
Which distribution better describes reconstructed hadronic W/top candidate masses in the selected DELPHES simulation sample?

## Structure
- `notebooks/top_quark_mass_fits.ipynb`: copy of `sigma_values_Dylan.ipynb`.
- `notebooks/top_quark_pt_selection_experiment.ipynb`: backup variant with explicit high/low leading-jet transverse-momentum selections.
- `figures/`: extracted existing output plots.
- `data/README.md`: missing input instructions.
- `docs/`: source provenance and limitations.

## Setup and run
Notebook metadata records Python **3.12.3**. In a Python 3.12 virtual environment:
```sh
python -m pip install -r requirements.txt
python -m jupyterlab notebooks
```
Obtain the original `tt_hadronic_testing.h5` and place it in `data/raw/`. The copied notebooks now use that relative path. Run from the notebook directory. Original scientific calculations and stored outputs are preserved. Full execution is blocked until the input is recovered; no replacement simulation is invented.

## Data source
The poster identifies DELPHES simulation. The notebook reads HDF5 groups under `INPUTS/Jets`, `INPUTS/BoostedJets`, and `TARGETS/FRt1`/`FRt2`. [TODO: obtain the exact download URL, generation settings, sample size, and dataset version from the project records or mentor.] The referenced HDF5 file was not found in the searched local folders. Keep the full dataset out of git.

## Poster and acknowledgments
[Poster and presentation](https://docs.google.com/presentation/d/10y8hE2Fxz_tV-AwOi3cw4b6ev6WDbbdFE-aLw1aaDs4/edit)

Acknowledgments: Professor Javier Duarte, mentor Daniel Primosch, and SDSC's Mentor Assistance Program. The institution follows the poster and research overview (UCSD), correcting the initial UCSC label. [TODO: specify Dylan's individual contributions versus Jake's.]

## Results and caveats
The poster lists Gaussian/Lorentzian chi-squared pairs 26.19/12.27, 10.16/1.92, 18.04/6.69 and 6.47/8.69. Separate notes and notebook variants report different values; do not merge them into one analysis. [TODO: identify which notebook settings reproduce the poster.] The poster describes a 250 GeV leading-jet invariant-mass threshold whereas the backup code uses leading-jet pT. Detector smearing is a proposed explanation, not a confirmed cause. No new physics conclusions are inferred during packaging.

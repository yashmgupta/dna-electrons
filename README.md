# dna-electrons

Compute total electrons for DNA sequences with toggles for backbone and phosphate charges.
Now includes **FASTA parsing** and **Biopython** integration.


## Install (from source)

```bash
git clone https://github.com/yashmgupta/dna-electrons.git
cd dna-electrons
python -m venv .venv && source .venv/bin/activate  # on Windows: .venv\Scripts\activate
pip install -U pip build
pip install -e .
```

## CLI

```bash
dna-electrons --seq ATGCAT --double --include-backbone --include-charge
dna-electrons --fasta sequences.fasta --output csv > results.csv
```

## Python API

```python
from dna_electrons import compute_electrons
from dna_electrons.io import compute_from_fasta

res = compute_electrons("ATGCAT", double_stranded=True, include_backbone=True, include_phosphate_charge=True)
for rec_id, r in compute_from_fasta("sequences.fasta", double_stranded=True):
    print(rec_id, r.total, r.breakdown)
```

## Contributing

- Run tests: `pytest -q`
- Lint (optional): add your preferred linter/formatter.

## License

MIT © 2025 Dr. Yash Munnalal Gupta

## How to Cite

If you use `dna-electrons`, please cite:

Gupta, Yash Munnalal. dna-electrons: A Python Package for Calculating Total Electron Counts in DNA Sequences. v2.0.4. DOI: [10.5281/zenodo.17347432](https://doi.org/10.5281/zenodo.17347432)

BibTeX:
```bibtex
@misc{Gupta2025,
  title={dna-electrons: A Python package for calculating total electron counts in DNA sequences},
  author={Gupta, Yash Munnalal},
  year={2025},
  doi={10.5281/zenodo.17347432},
  url={https://github.com/yashmgupta/dna-electrons}
}
```
Full paper: [paper/paper.pdf](/paper.pdf)  
Zenodo record: [https://zenodo.org/record/17347432](https://zenodo.org/record/17347432)

# OALFD
# OALFD: Online Active Learning Ensemble for Data Streams with Feature Drift

This repository provides the source code and dataset references for the paper
**"OALFD: Online Active Learning Ensemble for Data Streams with Feature Drift"**,
submitted to *Engineering Applications of Artificial Intelligence*.

OALFD is an online feature-relevance-aware active learning framework for data
streams under feature drift. It maintains a sliding-window decision forest
(DTSW) to estimate the currently relevant feature subset, decomposes each
instance into core / auxiliary / full-feature views (the three-view ensemble
E3C), and allocates labels by combining view-specific uncertainty with changes
in the estimated relevant-feature subset.

## Requirements

```bash
python >= 3.9
river
numpy
scikit-learn
pandas
```

Install with:

```bash
pip install -r requirements.txt
```

## Datasets

All datasets used in this study are **publicly available**. We do **not**
redistribute the original data here; please download each dataset from its
official source listed below. Synthetic streams (Agrawal, Sine, Mixed,
RandomTree, SEA / SEA100) are generated with the `river` library generators
and require no download.

### Synthetic streams (generated via `river`)
| Dataset | Source |
|---|---|
| Agrawal | `river.datasets.synth.Agrawal` |
| Sine | `river.datasets.synth.Sine` |
| Mixed | `river.datasets.synth.Mixed` |
| RandomTree | `river.datasets.synth.RandomRBF` / `RandomTree` generator |
| SEA / SEA100 | `river.datasets.synth.SEA` (SEA100 adds 100 noise features) |

River library: https://riverml.xyz/

### Real-world streams
| Dataset | Description | Official source |
|---|---|---|
| IoT | IoT network anomaly detection | https://www.kaggle.com/datasets / IoTID20 (Ullah & Mahmoud, 2020) |
| Cic (CICIDS) | Network intrusion detection | https://www.unb.ca/cic/datasets/ |
| Electricity | Electricity price prediction | https://datahub.io/machine-learning/electricity |
| Poker | Poker hand recognition | https://archive.ics.uci.edu/dataset/158/poker+hand |
| Yoga | Human activity recognition | https://www.timeseriesclassification.com/ |
| NOAA | Weather forecasting | https://www.ncei.noaa.gov/ |

> Replace the placeholder links above with the exact URLs you used if any
> differ. UCI Machine Learning Repository: https://archive.ics.uci.edu/

## Reproducing the experiments

```bash
# Example: run OALFD on a single stream
python run_oalfd.py --dataset agrawal --drift sudden --seed 0
```

All real-world datasets are processed in their original sequential order under
the standard prequential evaluation protocol. Results in the paper are averaged
over multiple runs (seeds).

## Data availability

All datasets used in this study are publicly available benchmark stream
datasets and can be accessed from their original sources listed above. The
source code in this repository supports full reproducibility of the reported
results.

## Citation

```bibtex

```

## License

Released under the MIT License (see `LICENSE`).

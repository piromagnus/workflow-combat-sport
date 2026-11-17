# Completing Fine-Grained Combat-Sports Annotations with Model-Assisted Review

Pierre Marrec, Alexandre Schortgen, Lionel Reveret — Inria, Grenoble, France

**MMSports '26** — 9th International ACM Workshop on Multimedia Content Analysis in Sports, co-located with ACM Multimedia 2026, Rio de Janeiro, Brazil.

[![Paper](https://img.shields.io/badge/paper-ACM%20DL-b31b1b)](https://doi.org/10.1145/3841455.3841527)
[![DOI](https://img.shields.io/badge/DOI-10.1145%2F3841455.3841527-blue)](https://doi.org/10.1145/3841455.3841527)
[![Code](https://img.shields.io/badge/code-coming%20soon-lightgrey)](#code-release)

> **Code release: coming soon.** This repository currently hosts the paper record only. The annotation pipeline, model checkpoints and evaluation scripts are being cleaned up and will be pushed here.

## Abstract

Combat-sports federations archive long competition videos, but experts cannot label every action. Existing labels therefore miss attacks, use rough time windows, or omit the technique. We present a model-assisted annotation pipeline: a temporal detector proposes attacks, a sport-specific filter removes duplicates or keeps valid overlaps, a classifier ranks likely techniques, and an expert accepts, corrects, or rejects each proposal. On judo, one expert judged 295 of 324 detector proposals that did not match existing labels (91.0%) to be useful missing attacks. In a timed pilot on 18 videos (120.62 min), the expert produced 180 correct standing-technique labels in 1.25 h. A modeled estimate of fully manual annotation for the same 180 labels is 3.51 h. After post-processing, detection recall is 0.618 mAR@0.5 on sparse judo and 0.886 on dense boxing. In-domain judo technique recognition reaches 49.70% top-1. We also report calibration, suggestion-list size, transfer to another competition, and agreement between two experts. Federation labels are not treated as complete ground truth.

## Method

Four stages, with the expert in the loop at the end:

1. **Detect** — a temporal action detector proposes candidate attacks over the full video.
2. **Filter** — a sport-specific rule set drops duplicates and keeps valid overlaps (e.g. a throw followed by a hold-down).
3. **Rank** — a technique classifier orders the candidate techniques for each proposal, producing a short suggestion list.
4. **Review** — the expert accepts, corrects or rejects every proposal, turning model output into fine-grained labels.

## Key results

| Setting | Result |
| --- | --- |
| Judo, detector proposals not matching existing labels judged useful | 295 / 324 (91.0%) |
| Timed pilot, 18 videos (120.62 min), standing techniques | 180 correct labels in 1.25 h |
| Modeled fully manual annotation, same 180 labels | 3.51 h |
| Detection recall after post-processing, sparse judo | 0.618 mAR@0.5 |
| Detection recall after post-processing, dense boxing | 0.886 mAR@0.5 |
| In-domain judo technique recognition | 49.70% top-1 |

The paper also reports classifier calibration, suggestion-list size, transfer to another competition, and inter-expert agreement.

## Code release

Planned contents of this repository:

- [ ] Pipeline code (detection → filtering → technique ranking → review interface)
- [ ] Evaluation scripts reproducing the recall and recognition numbers above

Watch or star the repository to be notified. Until then, please cite the paper.

## Citation

```bibtex
@inproceedings{marrec2026completing,
  author    = {Marrec, Pierre and Schortgen, Alexandre and Reveret, Lionel},
  title     = {Completing Fine-Grained Combat-Sports Annotations with Model-Assisted Review},
  year      = {2026},
  publisher = {Association for Computing Machinery},
  address   = {New York, NY, USA},
  booktitle = {Proceedings of the 9th International ACM Workshop on Multimedia Content Analysis in Sports},
  series    = {MMSports '26},
  pages     = {73--80},
  numpages  = {8},
  location  = {Rio de Janeiro, Brazil},
  doi       = {10.1145/3841455.3841527},
  url       = {https://doi.org/10.1145/3841455.3841527}
}
```

ACM Reference Format:

```text
Pierre Marrec, Alexandre Schortgen, and Lionel Reveret. 2026. Completing
Fine-Grained Combat-Sports Annotations with Model-Assisted Review. In
Proceedings of the 9th International ACM Workshop on Multimedia Content
Analysis in Sports (MMSports '26). ACM, New York, NY, USA, 73--80.
https://doi.org/10.1145/3841455.3841527
```

## Contact

Questions about the paper or the upcoming release: open an issue here, or reach Pierre Marrec (pierre.marrec@inria.fr).

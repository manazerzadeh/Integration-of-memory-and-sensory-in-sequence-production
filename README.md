# Integration of memory and sensory in sequence production

This repository contains analysis of experimental data alongside drift-diffusion style modelling of the sequential finger pressing task of the paper
> Nazerzadeh, A., Porwal, M., Pruszynski, J.A., Diedrichsen, J. 2025. Integration of memory and sensory in sequence production, *bioRxiv* [https://doi.org/10.1101/2025.09.10.675426](https://doi.org/10.1101/2025.09.10.675426)

## Contents

- `single_press_model.ipynb`: single-press modeling. One CONFIG block drives the whole run; Replicates RT/accuracy of experimental data.

- `sequence_model.ipynb`: sequence modeling that integrates visual and memory inputs. Replicates experimental data and predicts behavior in response to violations.

- `data_analysis.ipynb`: experimental data analysis for Experiments 1, 2, and 3.
- `data/`: CSV inputs to the analysis notebook.

## Quick Start

1. Open any notebook in Jupyter / VS Code.
2. Run cells top-to-bottom. Figures and summary DataFrames will appear inline.
3. For modeling, adjust the CONFIG/parameter blocks near the top (e.g., drifts, thresholds, window sizes) before re-running result cells.
4. For data analysis, ensure the CSVs listed in **Data files** are present in `data/`.

## Data files (for `data_analysis.ipynb`)

- `data/EXP1_subjs_blocks.csv`: Experiment 1 MT/ER across blocks and days (sessions 1–3).
- `data/EXP1_subjs.csv`: Experiment 1 MT/ER by window size and condition; includes day 4 violation.
- `data/EXP1_violation_subjs_presses.csv`: Experiment 1 RT and error rates at the changed digit position on day 4.
- `data/EXP2_violation_subjs_presses.csv`: Experiment 2 IPIs based on their distance to the violation.
- `data/EXP3_violation_subjs_presses.csv`: Experiment 3 IPIs based on their distance to the violation.

## Key Model Parameters (sequence_model.ipynb)

| Name | Meaning |
| --- | --- |
| `window` | Visible horizon |
| `visual_drift_coef` | Base visual evidence strength |
| `memory_drift_coef` | Base memory input strength |
| `diffusion` | Gaussian noise |
| `threshold` | Decision bound (evidence limit) |
| `alpha` | Leakage / decay rate |
| `beta` | Lateral inhibition strength |
| `visual_delay` | Sensory latency |
| `motor_delay` | Execution latency|
| `sensory_param` | Sensory input weights |
| `memory_param` | Memory input weights |
| `memory_drift_adaptive_coef_*` | Violation adaptation (activation/deactivation) |

## Citation

> **Integration of memory and sensory information in skilled sequence production**
> Amin Nazerzadeh, Medha Porwal, J. Andrew Pruszynski, Jörn Diedrichsen
> *bioRxiv* (2025). [https://doi.org/10.1101/2025.09.10.675426](https://doi.org/10.1101/2025.09.10.675426)

## License

MIT License

Copyright (c) 2025 Amin Nazerzadeh

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

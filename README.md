# CETUS — Continuous-time ECM for TTE Under Scenarios

A continuous-time battery simulation framework that couples a second-order Thevenin equivalent-circuit model (ECM) with an OCV–SOC lookup to predict smartphone Time-to-Empty (TTE) under realistic constant-power workloads.

**Paper:** IEEE ICCE Berlin 2026

[![Compile & Deploy](https://github.com/Zyphoriate/CETUS/actions/workflows/compile-and-deploy.yml/badge.svg)](https://github.com/Zyphoriate/CETUS/actions/workflows/compile-and-deploy.yml)
[📄 Download PDF](https://zyphoriate.github.io/CETUS/icce_berlin_2026.pdf)

## Features

- Second-order Thevenin ECM with implicit constant-power current solve (quadratic per-step)
- Debounced cutoff filter separating numerical feasibility from user-facing shutdown
- Temperature- and aging-dependent capacity/resistance from public battery datasets
- Component-resolved power decomposition (screen, CPU, WiFi, cellular, GPS, etc.)
- TTE elasticity sensitivity analysis ranking optimization levers

## Usage Profiles

| Profile | TTE (25 °C) |
|---------|------------|
| Idle    | 39.45 h    |
| Video   | 9.06 h     |
| Gaming  | 5.34 h     |
| Mixed   | 4.08 h     |

## Build Locally

```bash
latexmk -pdf -interaction=nonstopmode icce_berlin_2026.tex
```

Requires a TeX Live distribution with `IEEEtran.cls` (included) and standard packages
(`amsmath`, `booktabs`, `siunitx`, `subcaption`, `algorithmic`, `xcolor`, `url`, `cite`).

## CI/CD

GitHub Actions compiles the paper on every push and deploys the PDF to GitHub Pages.
See [`.github/workflows/compile-and-deploy.yml`](https://github.com/Zyphoriate/CETUS/blob/main/.github/workflows/compile-and-deploy.yml).

## Citation

```bibtex
@inproceedings{cetus2026,
  title     = {A Continuous-Time ECM–OCV Model for Smartphone Battery
               Time-to-Empty Prediction with Constant-Power Load and
               Debounced Cutoff},
  author    = {Author One and Author Two and Author Three},
  booktitle = {Proc. IEEE ICCE Berlin},
  year      = {2026}
}
```

- [ ] 示意图
- [ ] 订正baseline算法
- [ ] 校对baseline结果
- [ ] 完善结果解释
- [ ] 完善模型建立
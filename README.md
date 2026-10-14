<div align="center">

# Recommendation System Audit

### Auditing the Objective

**A Multi-Objective Bandit Framework and Reproducible Audit Protocol for Engagement-Based Recommendation Systems**

*Technical extension to “Engagement as Objective” · August 9, 2026*

**[Read the Paper](paper.pdf)** · **[Research Overview](#research-overview)** · **[Authors](#authors)** · **[Citation](#citation)**

---

**Recommender Systems · Multi-Objective Optimization · Algorithmic Auditing · Responsible AI**

</div>

## Research Overview

What should an auditor examine when a recommendation system is designed to maximize engagement?

This technical report develops an engineering and auditing framework for engagement-based recommendation systems. It brings predicted engagement, independently estimated content quality, and moral-emotional outrage into an explicit multi-objective specification, then examines how ranking constraints and exploration strategies affect the resulting trade-offs.

The report connects contextual bandits, fair ranking, and constrained learning with a practical audit checklist for examining disclosed ranking documentation and logged behavior.

> **Central question:** How can recommendation objectives and their consequences be made explicit, measurable, and auditable?

## What the Report Covers

| Component | Focus |
| :--- | :--- |
| **Multi-objective contextual bandit** | A reward specification incorporating engagement, content quality, and outrage indicators. |
| **Ranking filter** | A slate-level rejection rule designed to limit high-outrage exposure, with simulation-based analysis of the engagement–extremity trade-off. |
| **Exploration strategies** | A comparison of UCB1 and quality-aware Thompson Sampling, including a forced-exploration floor. |
| **Audit protocol** | A 22-item checklist organized into five domains, supported by worked examples. |
| **Calibration and limitations** | Subgroup calibration, estimator generalization, feedback loops, and strategic adaptation by content producers. |

## Reported Simulation Findings

The following figures are reported in the paper's abstract and worked analyses. They describe synthetic experiments, not measurements from deployed platforms.

| Metric | Result reported in the paper | Context |
| :--- | :--- | :--- |
| Cumulative outrage exposure | **21.1% lower** | Quality-aware Thompson Sampling compared with UCB1. |
| Cumulative engagement regret | **68.2% higher** | The corresponding cost in the same comparison; this is not a percentage decrease in engagement. |
| Evaluation horizon | **6,000 rounds across 8 seeds** | The exploration-strategy comparison. |
| Subgroup calibration error | **7.7× larger** | Simulated minority-language subgroup relative to the majority subgroup in the worked calibration example. |

See Sections 5–6 of [the full report](paper.pdf) for experimental context and interpretation. These results are presented as reported by the authors and have not been independently reproduced in this repository.

## Reading Guide

- **Sections 1–3:** Motivation, formal specification, and connections to prior research.
- **Section 4:** Ranking constraints and the engagement–extremity frontier.
- **Section 5:** Exploration, feedback loops, and separate regret and exposure metrics.
- **Section 6:** Audit checklist, calibration example, and illustrative scorecard.
- **Section 7:** Limits of mathematical auditing and adversarial adaptation.
- **Section 8:** Conclusion.

## Scope and Limitations

The framework examines whether a stated objective and its constraints are internally consistent and supported by observed behavior. It cannot determine, by mathematics alone, which objectives a platform ought to optimize.

Its practical usefulness depends on estimator validity, subgroup coverage, access to suitable documentation and logs, and continued evaluation as content producers adapt to ranking rules. The report discusses these limitations explicitly.

This README accompanies the technical report. It does not provide an executable implementation or reproduction package for the experiments.

## Authors

| Author | Affiliation listed in the report |
| :--- | :--- |
| **Ilgiz Satkynov** | De Anza College |
| **Baian Abdyrasulova** | Jefferson Community College |
| **Ivan Krutchenko** | Foothill College / De Anza College |

## Citation

If you reference this report, you may use the following BibTeX entry:

```bibtex
@techreport{satkynov2026auditing,
  title  = {Auditing the Objective: A Multi-Objective Bandit Framework
            and Reproducible Audit Protocol for Engagement-Based
            Recommendation Systems},
  author = {Satkynov, Ilgiz and Abdyrasulova, Baian and Krutchenko, Ivan},
  year   = {2026},
  month  = aug,
  type   = {Technical report},
  note   = {Technical extension to "Engagement as Objective"}
}
```

---

<div align="center">

**[Read the full technical report →](paper.pdf)**

</div>

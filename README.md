# osmos-agent-eval

Artifact repository for the paper:

> **Giving the Agent the Evidence It Asked For: Fidelity-Aware Frozen Replay for Regression Evaluation of LLM Operations Agents**
> Wenbo Zhou. Submitted to the Industrial Track of SANER 2027 (under review).

## Status

**The code is not yet available.** It is currently going through Xiaomi's internal open-source review. This repository will be updated once the review is complete. To be notified, watch this repository or contact the author (see below).

## What will be released

Subject to the outcome of the review, we plan to release:

- **Replay engine**: the fidelity-aware replay engine described in Section IV of the paper, including
  - evidence verification (object and time-window check $F$ before a recording is served),
  - per-source fallback (deciding per data source whether a live re-query can be trusted),
  - time alignment (pinning the prompt clock to the diagnosis time and clipping live queries at the latest observable instant),
  - equivalent-form matching, partial coverage, and tool-error handling.
  Each mechanism can be switched on and off individually, matching configurations C0–C5 in the paper.
- **Evaluation scripts**: call replay, the fidelity check $F$, the fidelity-adjusted evidence score (FR), and the ablation over C0–C5.
- **Statistics scripts**: bootstrap confidence intervals, sensitivity analysis of the re-query agreement coefficients, and paired McNemar tests with Holm correction.
- **Plotting scripts** for the figures in the paper.

## What will not be released

The recordings, tool responses, and diagnosis sessions used in the paper come from Xiaomi's production environment. They contain internal sensitive information such as monitoring metrics and logs, and therefore cannot be released. The same applies to the manual labels and run logs, which are tied to these data.

Without the production data, the released code cannot reproduce the exact numbers in the paper. We intend to document the input formats so that the engine and evaluation scripts can be applied to other recorded agent sessions.

## Contact

Wenbo Zhou — zhouwenbo@xiaomi.com

## Citation

The paper is under review. A citation entry will be added here if it is accepted.

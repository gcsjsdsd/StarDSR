# StarDSR

**StarDSR: A Lightweight Mamba-based Framework for Real-Time End-to-End Chinese Dysarthric Speech Reconstruction on Edge Devices**

🔗 **Demo page: [gcsjsdsd.github.io/StarDSR](https://gcsjsdsd.github.io/StarDSR/)**

## Overview

StarDSR transforms impaired dysarthric speech into clear, natural audio while **preserving the speaker's own timbre** — no healthy reference speech is needed at inference. The framework repurposes StarGANv2-VC into an identity-preserving restoration pipeline:

- **RSR block (Rapid Spectrogram Refinement)** — stacked Mamba layers with a FastSpeech-style length regulator; linear-time sequence modeling restores phonetic clarity in prolonged, irregular dysarthric speech.
- **Timbre encoder** — pretrained ECAPA-TDNN + Mamba with a vector-quantization bottleneck that extracts stable speaker identity while filtering out pathological artifacts.
- **AdaIN-based encoder–decoder** — voiced-masked, log-domain F₀ conditioning corrects pitch instability and reinforces speaker similarity.
- **Dual discriminators** — real/fake and dysarthric/clear, jointly enhancing naturalness and intelligibility.

## Key results

| Metric | Original speech | StarDSR |
|---|---|---|
| CER, all dysarthric speakers | 23.2% | **18.1%** (−22% relative) |
| RTF @ RTX 4090D | — | **0.21** |
| RTF @ OrangePi AIpro (8T) edge board | — | **0.92** (real time) |
| Naturalness MOS (speakers 01 / 04 / 06) | 3.49 / 2.78 / 3.11 | **4.19 / 3.89 / 3.91** |

Full comparisons, ablations, and framework figures are on the [demo page](https://gcsjsdsd.github.io/StarDSR/).

## This repository

- `index.html`, `images/` — the GitHub Pages demo site served at the link above.

<!-- TODO: 论文正式发表/公开后补充作者信息并替换下面的引用条目 -->

## Citation

```bibtex
@inproceedings{stardsr2026,
  title  = {StarDSR: A Lightweight Mamba-based Framework for Real-Time End-to-End Chinese Dysarthric Speech Reconstruction on Edge Devices},
  author = {Anonymous},
  year   = {2026},
  note   = {under review}
}
```

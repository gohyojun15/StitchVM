<div align="center">

# Stitched Value Model for Diffusion Alignment

[Hyojun Go](https://gohyojun15.github.io/)<sup>1</sup> &nbsp;·&nbsp;
[Hyungjin Chung](https://hyungjin-chung.github.io/) &nbsp;·&nbsp;
[Prune Truong](https://prunetruong.com/)<sup>2</sup> &nbsp;·&nbsp;
[Goutam Bhat](https://goutamgmb.github.io/)<sup>2</sup> &nbsp;·&nbsp;
[Li Mi](https://limirs.github.io/)<sup>1</sup> &nbsp;·&nbsp;
[Zhaochong An](https://zhaochongan.github.io/)<sup>3</sup>
<br>
[Zixiang Zhao](https://zhaozixiang1228.github.io/)<sup>1</sup> &nbsp;·&nbsp;
[Dominik Narnhofer](https://baug.ethz.ch/departement/personen/mitarbeiter/personen-detail.MzM5ODU5.TGlzdC82NzksLTU1NTc1NDEwMQ==.html)<sup>1</sup>
<br>
[Serge Belongie](https://sergebelongie.github.io/)<sup>3</sup> &nbsp;·&nbsp;
[Federico Tombari](https://federicotombari.github.io/)<sup>2</sup> &nbsp;·&nbsp;
[Konrad Schindler](https://prs.igp.ethz.ch/group/people/person-detail.schindler.html)<sup>1</sup>

<sup>1</sup>ETH Zürich &nbsp;·&nbsp;
<sup>2</sup>Google &nbsp;·&nbsp;
<sup>3</sup>University of Copenhagen

[**Project page**](https://gohyojun15.github.io/StitchVM/) &nbsp;|&nbsp;
[**Paper (PDF)**](https://gohyojun15.github.io/StitchVM/static/stitchvm.pdf) &nbsp;|&nbsp;
**arXiv** (coming soon) &nbsp;|&nbsp;
**Code** (coming soon)

</div>

---

## TL;DR

**StitchVM** turns any pretrained pixel reward model (CLIP, HPSv2, Aesthetic Predictor, …) into a **value model that scores noisy diffusion latents directly** — at small compute cost. Drop the resulting value model into any diffusion-alignment recipe (DPS, FK steering, DRaFT, DiffusionNFT, …) and each gets cheaper *and* often better at the same time.

> A pretrained reward model only sees clean images. Diffusion alignment needs reward on the **noisy intermediate latents** generated during sampling. Existing workarounds either rely on the biased Tweedie approximation or expensive Monte-Carlo rollouts. StitchVM avoids both by **stitching** a pretrained diffusion backbone (which natively handles noisy latents) to a pretrained reward model — joined by a thin **stitching layer** and briefly finetuned together with the reward tail. The result is a hybrid that inherits the reward model's predictive skill but now consumes $\mathbf{z}_t$ directly.

See the [project page](https://gohyojun15.github.io/StitchVM/) for figures, results, and the four alignment recipes we plug into.

## Code release

> ⚠️ **The code release is in preparation.** Star or watch this repository to be notified.

We will release training scripts, pretrained StitchVM checkpoints (SD 3.5 Medium / Large, FLUX.1-dev × CLIP / DFN-CLIP / HPSv2 / Aesthetic Predictor), and reference plug-ins for DPS, FK steering, DRaFT, and DiffusionNFT.

## Citation

```bibtex
@article{go2026stitchvm,
    title   = {Stitched Value Model for Diffusion Alignment},
    author  = {Go, Hyojun and Chung, Hyungjin and Truong, Prune and Bhat, Goutam
               and Mi, Li and An, Zhaochong and Zhao, Zixiang and Narnhofer, Dominik
               and Belongie, Serge and Tombari, Federico and Schindler, Konrad},
    journal = {arXiv preprint},
    year    = {2026}
}
```

## Contact

For questions about the method or the paper, please open a GitHub issue or contact [Hyojun Go](mailto:gohyojun15@gmail.com).

---

<sub>This repository hosts the project page. It is built on the [prs-eth project page family](https://github.com/prs-eth/rollingdepth), which extends the [Nerfies](https://github.com/nerfies/nerfies.github.io) template.</sub>

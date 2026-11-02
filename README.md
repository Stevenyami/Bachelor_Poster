# Surgical Video Segmentation with SAM2 and SASVi

**Bachelor’s thesis · Computer Vision for Healthcare · Fraunhofer IGD / TU Darmstadt**

Fine-tuning foundation models for surgical scene understanding: this thesis studies **SAM2** on ophthalmic surgical images and its integration into **SASVi** for video segmentation.

**Author:** Steve Jordi Nyami Gochui  
**Thesis title:** *Fine-Tuning SAM2 for Temporally Consistent Semantic Segmentation of Surgical Videos with SASVi*  
**Date shown on the poster:** November 27, 2025

**Thesis grade:** 1.0. Nominated for the **Freudenberg Award Digital Science 2026**, among the top three bachelor's theses at TU Darmstadt.

[**Read the thesis poster (PDF)**](Bachelor_Poster.pdf)

## Research question

How does domain-specific fine-tuning affect SAM2’s segmentation accuracy, and how does the adapted model behave within a surgical video pipeline that automatically refreshes prompts?

## Approach

- Fine-tune SAM2 on **CaDIS**, a dataset for cataract surgery image segmentation.
- Integrate SAM2 into **SASVi**, using overseer models to trigger automatic re-prompting as the scene changes.
- Compare original and fine-tuned SAM2.1 models, with **U-Net (MONAI)** as an additional baseline in the SASVi evaluation.
- Evaluate spatial accuracy using **mIoU and Dice**, alongside the temporal measures reported in the poster.
- Examine qualitative transfer to **OphNet** surgical videos.

## Selected results

The poster’s separate **image test evaluation** reports:

| Model | mIoU | Dice |
| --- | ---: | ---: |
| SAM2.1-Tiny, original weights | 0.6159 | 0.7451 |
| SAM2.1-Tiny, fine-tuned | 0.7970 | 0.8829 |
| SAM2.1-Large, original weights | 0.6465 | 0.7619 |
| SAM2.1-Large, fine-tuned | **0.8209** | **0.8993** |

These values belong to the image test table, **not** the SASVi video evaluation. Results within SASVi vary by model, overseer and metric: fine-tuning does not improve every spatial or temporal measure. The poster includes the full comparison and qualitative examples.

## Repository contents and scope

| File | Contents |
| --- | --- |
| [Bachelor_Poster.pdf](Bachelor_Poster.pdf) | Research motivation, datasets, pipeline, quantitative comparisons and qualitative results |

This repository shares the **thesis poster**. Training code, model checkpoints and a reproducible experiment configuration are not included. The reported results are research findings; the poster does not establish clinical validation or deployment readiness.

## Research context

The poster cites the original work on SAM2, SASVi, CaDIS, OphNet and U-Net. See its references for attribution and dataset context.

**Keywords:** computer vision, medical image analysis, surgical video analysis, semantic segmentation, video segmentation, SAM2, SASVi, domain adaptation.

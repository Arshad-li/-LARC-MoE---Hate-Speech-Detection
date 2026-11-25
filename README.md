# LARC-MoE: Hate Speech Detection

LARC-MoE: Layer-Attentive Residuals Contrastive Learning with Mixture-of-Experts for Hate Speech Detection.

This repository accompanies a co-authored research manuscript that is currently being revised after review. It is not yet published.

## Problem

Hate speech and merely offensive language use similar words, so a standard fine-tuned transformer can blur the two classes in its internal representation. Most models classify from the final layer only and train with ordinary cross-entropy loss.

## Method

LARC-MoE combines three ideas:

1. **Layer-attentive residuals.** The model learns a weighted combination of all transformer layers, plus a shortcut from the last layer, instead of using only the final layer.
2. **Supervised contrastive learning.** Examples of the same class are pulled closer together and examples of different classes are pushed apart. The temperature adapts per example, so ambiguous posts are treated more gently.
3. **Mixture-of-Experts classification head.** Several small classifiers (experts) and a gating network that decides how much to trust each expert for a given input.

## Setup

* Five backbones were tested: DistilBERT, TinyBERT, RoBERTa, ALBERT and HateBERT.
* The task is binary: hate speech versus offensive language, using a public hate speech dataset reduced to those two classes.

## Status

The manuscript is under revision. The revision re-runs the evaluation with the data split before any oversampling, replaces estimated ablation figures with full runs, and compares against baselines on the same two-class data. Results will be added here after those runs are complete.

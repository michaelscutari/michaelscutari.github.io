---
title: "Sequence Clustering Library"
date: 2025-01-25
category: "personal"
priority: 2
header_image: "/assets/images/cluster.png"
description: "A Python library for clustering biological sequences and splitting datasets into train/test splits while preserving cluster integrity."
layout: "project"
status: "in-progress"
technologies:
  - Python
  - Pandas
  - MMseqs2
---

# Introduction

*This project is currently in development. Feel free to contact me with suggestions for new features or issues.*

This project is a Python library designed for clustering biological sequences and splitting datasets into train/test splits while maintaining cluster integrity. It leverages [MMseqs2](https://github.com/soedinglab/MMseqs2) for sequence clustering and uses `pandas` for data manipulation.

The library makes it easy to preprocess sequence datasets, cluster them into representative sequences, and create splits that respect clustering boundaries. It's ideal for bioinformatics workflows where sequence relationships matter.

---

## Vision

The goal of this library is to simplify the preprocessing of biological sequence datasets. By integrating MMseqs2 with Python, users can easily cluster sequences and ensure that no clusters bleed into both the training and testing datasets. The functionality is designed to be intuitive, efficient, and adaptable.

---

## Features

1. **Sequence Clustering**:
   Use MMseqs2 to cluster biological sequences and add a `representative_sequence` column to a DataFrame.

2. **Train/Test Splitting**:
   Split datasets into train and test sets while ensuring no overlap of sequences across clusters. This maintains the integrity of sequence relationships.

---
# Links
- [Codebase](https://github.com/michaelscutari/mmseqspy)

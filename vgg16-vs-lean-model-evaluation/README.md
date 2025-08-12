# VGG vs Lean Model: Classification Performance Comparison
## Overview
This project compares two deep learning models for binary image classification:
1. **VGG16-based Benchmark Model** – a well-known, high-capacity convolutional neural network architecture that often achieves strong accuracy but comes with high computational and storage costs.
2. **Lean Model - MobileNet** –  a lightweight, efficient convolutional neural network specifically designed for mobile and embedded vision applications, utilizing depthwise separable convolutions to significantly reduce parameters and computational requirements while maintaining competitive accuracy.
The purpose of this comparison is to explore the trade-offs between model performance and efficiency, and to determine whether a lean architecture can serve as a practical alternative to a heavy benchmark model like VGG.
## Business Context
In many real-world scenarios, especially in industries like agriculture, manufacturing, and retail, quick and reliable classification of items is essential.  
For example, a fruit supplier may need to automatically classify products into **sellable** vs. **non-sellable** categories using an automated quality inspection system.  
While a large benchmark model (e.g., VGG) might provide excellent accuracy, its high computational demands may make it unsuitable for on-device or real-time applications.  
By comparing the benchmark model with a lean alternative, this project aims to identify whether we can maintain accuracy while drastically reducing resource requirements — enabling deployment in edge devices, mobile systems, or low-cost environments.
## Why Compare VGG vs. Lean?
- **VGG Benchmark Model**: Acts as a performance reference point; widely used in academic and research contexts.
- **Lean Model**: Designed for resource efficiency; ideal for scenarios where speed, hardware constraints, or cost make large models impractical.
- **Goal**: Determine whether the lean model can achieve comparable accuracy with reduced computational complexity.
## Project Structure
- `vgg16_vs_lean_classification.ipynb` – Main notebook containing data preprocessing, model training, evaluation, and comparison.
- `data/` – Dataset used for training and testing (not included in this repository; see dataset link below).
- `README.md` – Project documentation.
- `LICENSE` – Project license file (aligned with dataset license).
## Dataset Attribution
This project uses the **Fruits-360** dataset, available at [https://github.com/fruits-360](https://github.com/fruits-360).  
The dataset is licensed under the [Creative Commons Attribution-ShareAlike 4.0 International License (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/).  
Copyright (c) 2017-, Mihai Oltean.

**Changes made:** [brief description of preprocessing or augmentation steps].

**Dataset Citation:**  
- Mihai Oltean, Fruits-360 dataset, 2017-  
- Horea Muresan, Mihai Oltean, "Fruit recognition from images using deep learning", Acta Univ. Sapientiae, Informatica, Vol. 10, Issue 1, pp. 26-42, 2018.

This project is not endorsed by the original dataset authors.

## License
This project is released under the [Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/) license, in compliance with the dataset license requirements.


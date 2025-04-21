# asp-project-II
# Functional Distance Measures for Detecting Non-linear Dependencies

This repository contains the implementation and analysis for Project 8 of the Applied Stochastic Processes course (MATH F424), focusing on quantifying correlations between random variables using functional distance measures.

## Project Overview

Traditional correlation measures like Pearson's correlation coefficient are limited to detecting linear relationships. This project explores more sophisticated approaches to quantify dependencies between random variables, particularly focusing on:

1. Using functional distance measures between joint and marginal probability distributions
2. Detecting and measuring non-linear dependencies
3. Comparing different measures across various relationship types
4. Developing a composite measure that combines multiple approaches

## Contents

- `correlation_measures.py`: Core implementation of various correlation measures
- `correlation_comparison.py`: Framework for comparing measures across different relationship types
- `Project8_NonlinearDependency.ipynb`: Jupyter notebook with complete analysis and visualizations
- `report/`: Directory containing the LaTeX report and figures
- `data/`: Example synthetic datasets for testing

## Implemented Correlation Measures

The repository implements and compares the following correlation measures:

- **Traditional Measures**
  - Pearson's correlation coefficient
  - Spearman's rank correlation
  - Kendall's tau

- **Distribution-based Measures**
  - KL divergence between joint and product distributions
  - Jensen-Shannon divergence

- **Advanced Measures**
  - Distance correlation
  - Mutual information (k-nearest neighbors estimation)
  - Binary Expansion Testing (BET)

- **Composite Measure**
  - Weighted combination of multiple measures

## Key Features

- **Synthetic Data Generation**: Create datasets with various relationship types (linear, quadratic, sine, circle, etc.)
- **Visualization Tools**: Compare joint distributions vs. product of marginals
- **Comprehensive Evaluation**: Assess detection power, computational efficiency, and noise sensitivity
- **Composite Measure Optimization**: Test different weight configurations for optimal performance

## Getting Started

### Prerequisites

```
numpy
pandas
matplotlib
seaborn
scipy
scikit-learn
```

### Installation

```bash
git clone https://github.com/ankit-prajapati/stochastic-process-projects.git
cd stochastic-process-projects
pip install -r requirements.txt
```

### Usage

```python
from correlation_measures import (
    pearson_correlation, distance_correlation, 
    binary_expansion_test, distribution_divergence,
    composite_measure
)

# Generate data with a quadratic relationship
x, y = generate_data('quadratic', n_samples=1000, noise_level=0.1)

# Calculate correlation using different measures
pearson = pearson_correlation(x, y)
dcorr = distance_correlation(x, y)
js_div = distribution_divergence(x, y, method='js')
composite = composite_measure(x, y)

print(f"Pearson: {pearson:.4f}")
print(f"Distance Correlation: {dcorr:.4f}")
print(f"JS Divergence: {js_div:.4f}")
print(f"Composite: {composite:.4f}")
```

## Results

Our analysis demonstrates that:

1. Traditional correlation measures fail to detect many non-linear dependencies
2. Distance correlation and Jensen-Shannon divergence show strong performance across relationship types
3. The composite measure achieves 100% correct identification in our tests
4. Different measures offer different trade-offs between detection power and computational efficiency


## Authors

- **Ankit Prajapati** - Department of Mathematics, BITS Pilani

## Acknowledgments

- Prof. Nirman Ganguly for guidance and supervision
- Székely et al. for the distance correlation methodology
- Zhang et al. for the Binary Expansion Testing approach

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Citation

If you use this code in your research, please cite:

```
@misc{prajapati2025functional,
  author = {Prajapati, Ankit},
  title = {Functional Distance Measures for Detecting Non-linear Dependencies},
  year = {2025},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/nyssaleo/asp-project-II}}
}
```

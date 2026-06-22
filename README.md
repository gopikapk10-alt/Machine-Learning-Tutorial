
## What is included

- `tutorial.pdf` - PDF tutorial, under 2000 words.
- `tutorial.html` - self-contained web-page version of the same tutorial with embedded figures.
- `tutorial.md` - editable source text for the tutorial.
- `notebooks/svm_kernel_tutorial.ipynb` - reproducible Jupyter notebook used to create the figures and results.
- `src/svm_kernel_demo.py` - Python script version of the demonstration.
- `src/build_tutorial_pdf.py` - optional script used to regenerate `tutorial.pdf`.
- `src/update_placeholders.py` - helper script to insert your GitHub URL/name before submission.
- `figures/` - generated figures and small CSV result summaries.
- `requirements.txt` - Python dependencies.
- `LICENSE` - MIT licence.

## Repository structure

```
.
├── README.md
├── LICENSE
├── requirements.txt
├── tutorial.pdf
├── tutorial.html
├── tutorial.md
├── notebooks/
│   └── svm_kernel_tutorial.ipynb
├── src/
│   ├── svm_kernel_demo.py
└── figures/
    ├── 01_dataset.png
    ├── 02_kernel_comparison.png
    ├── 03_rbf_gamma_c.png
    ├── 04_cv_heatmap.png
    ├── kernel_comparison.csv
    ├── rbf_sensitivity.csv
    └── results_summary.csv
```

## How to run the code

1. Create and activate a Python environment, for example:

```bash
python -m venv .venv
source .venv/bin/activate      # macOS/Linux
# .venv\Scripts\activate       # Windows PowerShell
```

2. Install the requirements:

```bash
pip install -r requirements.txt
```

3. Run the notebook:

```bash
jupyter notebook notebooks/svm_kernel_tutorial.ipynb
```

Or run the script version:

```bash
python src/svm_kernel_demo.py
```

The figures and result CSV files will be written to `figures/`.

## Main result

On the synthetic two-moons demonstration data:

| Model | Test accuracy |
|---|---:|
| Linear SVM | 0.843 |
| Degree-3 polynomial SVM | 0.935 |
| RBF SVM, C=1, gamma=1 | 0.972 |
| Cross-validation selected RBF SVM | 0.972 |

The 5-fold grid search selected `C = 10` and `gamma ≈ 1.78` for the RBF SVM.

## Accessibility notes

- Figures use the Okabe-Ito colour-blind-safe blue/orange palette.
- Classes are differentiated using both colour and marker shape.
- The web page includes descriptive alt text for figures.
- The tutorial text avoids relying on colour alone when explaining plots.

## References

- Boser, B. E., Guyon, I. M., & Vapnik, V. N. (1992). *A training algorithm for optimal margin classifiers*. Proceedings of COLT. https://doi.org/10.1145/130385.130401
- Cortes, C., & Vapnik, V. (1995). *Support-vector networks*. Machine Learning, 20, 273-297. https://doi.org/10.1007/BF00994018
- scikit-learn developers. *SVC documentation*. https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVC.html
- scikit-learn developers. *RBF SVM parameters example*. https://scikit-learn.org/stable/auto_examples/svm/plot_rbf_parameters.html

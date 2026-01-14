# Drug Toxicity Prediction with Machine Learning
#Results 

#Baseline Model: Logistic Regression

A multitask logistic regression model was trained using ECFP (Morgan) fingerprints (1024 bits) with a scaffold split to ensure realistic chemical generalisation. Performance was evaluated using ROC-AUC, the standard metric for imbalanced toxicity classification tasks.

Mean test ROC-AUC: 0.688

Performance varied across assays, reflecting known differences in task difficulty and label sparsity.

Stronger performance was observed for receptor-binding tasks (e.g. NR-AR, NR-AhR) compared to stress-response endpoints.

This baseline establishes a transparent and interpretable reference point for subsequent model comparisons.

#Gradient Boosted Trees: XGBoost

To capture non-linear structure in the molecular feature space, an XGBoost classifier was trained independently for each toxicity task using the same scaffold split and molecular representations.

Mean test ROC-AUC: 0.722

Mean improvement over logistic regression: +0.033 ROC-AUC

Notable task-level improvements:

NR-AR-LBD: +0.104 ROC-AUC

SR-MMP: +0.082 ROC-AUC

NR-AhR: +0.067 ROC-AUC

SR-p53: +0.066 ROC-AUC

Several tasks showed modest or neutral gains, highlighting task-specific limits of tree-based models under sparse-label conditions.

#Interpretation

These results demonstrate that:

Non-linear models provide consistent performance gains over linear baselines on chemical toxicity prediction tasks.

Scaffold splitting meaningfully challenges models, reinforcing the importance of chemically realistic evaluation.

Model performance varies substantially by endpoint, underscoring the heterogeneous biological mechanisms represented in Tox21.

Overall, XGBoost offers a robust and computationally efficient improvement over logistic regression while maintaining strong generalisation to unseen chemical scaffolds.

#Reproducibility

All results are fully reproducible using the notebooks provided in the notebooks/ directory.
Raw evaluation outputs are generated programmatically and saved locally during execution.

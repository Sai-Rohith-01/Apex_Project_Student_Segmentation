# Student Engagement Segmentation for Early Academic Intervention

An unsupervised machine learning project using K-Means and Hierarchical Clustering on LMS interaction data (`xAPI-Edu-Data`, $N=478$) to segment learners for proactive academic advising without using grade or attendance labels during training.

## Key Highlights
* **Leakage-Free Pipeline:** Trained on 5 standardized engagement features (`raisedhands`, `VisITedResources`, `AnnouncementsView`, `Discussion`, and `Log_Active_to_Passive_Ratio`).
* **High Reproducibility:** Log-transforming the right-tailed engagement ratio boosted random-seed stability across 10 seeds to **Mean ARI = 0.9954** (`k=3`).
* **Unseen Holdout Generalization (80/20 Split):** Validated on unseen students ($N=96$, **Silhouette = 0.3011**), identifying three distinct behavioral groups:
  1. **Disengaged / High-Risk Learners (34.4%):** 66.7% low-performing (`Class L`), 75.8% chronic absences (`Above-7`).
  2. **Fully Engaged Learners (27.1%):** 96.2% mid-to-high performing (`Class M/H`).
  3. **Content-Focused Quiet Learners (38.5%):** High resource views, low forum posts, yet **94.6% `Class M/H`**—preventing false-alarm advisor outreach.
* **Key Failure-Mode Finding:** 100% (3/3) of failing students inside the engaged clusters had `Above-7` absence days, showing that combining LMS clustering with attendance flags catches missed risk cases.

## Files
* `Apex_Project_Student_Segmentation.ipynb` — Complete end-to-end data cleaning, EDA, feature engineering, clustering experiments, and unseen holdout evaluation.

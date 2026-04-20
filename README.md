# Text Analytics - SemEval 2015 Figurative Language
Project for the Text Analytics exam (A.Y. 2023/2024, University of Pisa - instructor: Laura Pollacci). The repository contains the full workflow for SemEval-2015 Task 11 on figurative language, with preprocessing, two classification tasks, and a short explainability study, all implemented in Python notebooks.

## Repository Contents
- `Group2_Preprocess.ipynb`: data understanding and preprocessing; builds features (frames, word frequencies, SenticNet, WordNet synonyms, vectorizers) and prepares splits for downstream tasks.
- `Group2_ClassificationTask1.ipynb`: models for **figurative vs. non-figurative** classification using classical ML, word embeddings, and transformer baselines.
- `Group2_ClassificationTask2.ipynb`: models for **sarcastic vs. ironic** classification with classical ML and transformers.
- `Group2_Explainability.ipynb`: lightweight explainability on trained models (tree-based visualizations and diagnostics).
- `dataset_raw/`: original SemEval-2015 resources  
  - `figurative_clean`: tweet ID + text only  
  - `figurative_clean_onlyframes`: frames + tweet ID  
  - `task-11-training-data`: tweet ID + score  
  - `ironicFRAMES`: ironic tweet IDs with score and frames  
  - `sarcasticFRAMES`: sarcastic tweet IDs with score and frames  
  - `text_dataset`: merged, deduplicated text dataset derived from the first three sources
- `dataset_first_task/`: preprocessed train/test splits for figurative vs. non-figurative classification, in multiple variants (text + frames + synonym aggregates, with/without SenticNet features, with CountVectorizer, with feature selection).
- `dataset_second_task/`: preprocessed train/test splits for sarcastic vs. ironic classification, matching the variants above (with CountVectorizer and optional SenticNet features, plus feature selection).
- `Text_Analytics_Report.pdf`: concise write-up of the project.
- `README_TXA_group2.txt`: original Italian notes describing the dataset organization.

## Quickstart (local execution)
1. **Environment**: Python 3.10+ recommended. Create a virtual environment, e.g. `python -m venv .venv && source .venv/bin/activate`.
2. **Install dependencies** (CPU-friendly set):  
   `pip install pandas numpy scikit-learn seaborn matplotlib gensim torch torchvision torchaudio transformers tensorflow imbalanced-learn nltk senticnet wordfreq dtreeviz graphviz`
   - `graphviz` may also require a system package (e.g., `apt-get install graphviz`) for visualization.
3. **NLTK data**: download the required corpora:  
   `python -m nltk.downloader punkt stopwords wordnet`
4. **Open the notebooks**: `jupyter notebook` (or `jupyter lab`) and run in order:  
   1) `Group2_Preprocess.ipynb` -> 2) `Group2_ClassificationTask1.ipynb` -> 3) `Group2_ClassificationTask2.ipynb` -> 4) `Group2_Explainability.ipynb`.
   Outputs are already saved in the committed notebooks if you prefer to read results without re-running.

## Notes
- The preprocessed datasets in `dataset_first_task/` and `dataset_second_task/` are the outputs of `Group2_Preprocess.ipynb`; you can start from them to skip feature-building time.
- No packaged CLI is provided; the workflow is notebook-driven to keep the analysis transparent for the exam setting.

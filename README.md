# TOPSIS-Based Selection of Pre-trained Conversational Models

## Overview
This project applies the Technique for Order Preference by Similarity to Ideal Solution (TOPSIS), a multi-criteria decision-making (MCDM) method, to identify the most suitable pre-trained text conversational model. The selection is based on a balanced evaluation of performance, efficiency, and human preference metrics.

The implementation is carried out in Python using Google Colab, and the final results are visualized through tables and graphs for interpretability.

## NOTE: The notebook was created in Google Colab. If GitHub preview fails, please download the file and open it in Jupyter or Colab.

---

## Problem Statement
Apply TOPSIS to find the best pre-trained model for text conversational tasks.

---

## Models Considered
The following pre-trained conversational and instruction-tuned models were evaluated:

1. DialoGPT  
2. BlenderBot  
3. FLAN-T5  
4. T5  
5. LLaMA-2-Chat (included using benchmark data due to licensing and hardware constraints)

---

## Evaluation Criteria
The models were compared using the following criteria:

| Criterion         | Description                                      | Type    |
|------------------|--------------------------------------------------|---------|
| BLEU Score        | Measures response similarity to reference text  | Benefit |
| Inference Time    | Average response generation time                | Cost    |
| Model Size (MB)   | Memory footprint of the model                   | Cost    |
| Human Evaluation  | Reported human preference score from literature | Benefit |

Benefit criteria are maximized, while cost criteria are minimized during TOPSIS computation.

---

## Experimental Setup
- Platform: Google Colab  
- Programming Language: Python  
- Dataset: Blended Skill Talk  
- Libraries:
  - transformers
  - datasets
  - evaluate
  - numpy
  - pandas
  - matplotlib

All runnable models were evaluated experimentally. LLaMA-2-Chat was incorporated using published benchmark values due to reproducibility and resource limitations.

---

## Methodology
1. Collect performance metrics for each model.
2. Construct the decision matrix.
3. Normalize the matrix using vector normalization.
4. Apply criterion weights.
5. Determine ideal best and ideal worst solutions.
6. Compute separation measures.
7. Calculate TOPSIS scores and rank the models.

---

## Results

### Decision Matrix and TOPSIS Scores

| Model           | BLEU     | Inference Time | Model Size (MB) | Human Eval | TOPSIS Score | Rank |
|-----------------|----------|----------------|-----------------|------------|--------------|------|
| DialoGPT        | 0.009075 | 0.071588       | 621.94          | 3.6        | 0.660078     | 1    |
| FLAN-T5         | 0.000000 | 0.241761       | 293.58          | 4.3        | 0.504170     | 2    |
| LLaMA-2-Chat    | 0.022000 | 0.950000       | 7000.00         | 4.5        | 0.471635     | 3    |
| T5              | 0.000000 | 0.429662       | 230.81          | 3.9        | 0.471017     | 4    |
| BlenderBot      | 0.000000 | 0.567530       | 1508.92         | 4.1        | 0.403042     | 5    |

---

## Visualizations

### TOPSIS Score Comparison
The following bar chart illustrates the relative TOPSIS scores of all evaluated conversational models.

<img width="790" height="490" alt="image" src="https://github.com/user-attachments/assets/e3194939-1e74-4bf0-9318-bb797eb9d9c5" />


### Final Ranking of Models
This plot presents the final ranking of models based on TOPSIS scores, where a lower rank value indicates better performance.

<img width="790" height="490" alt="image" src="https://github.com/user-attachments/assets/d6f199cd-0d06-45d6-97d6-d0dabf7c5890" />


---

## Discussion
The results indicate that DialoGPT achieves the highest TOPSIS score due to its strong balance between computational efficiency and acceptable conversational quality. Although LLaMA-2-Chat demonstrates superior response quality and human evaluation scores, its large model size and higher inference time negatively impact its overall ranking. This highlights the trade-off between performance and resource efficiency in conversational AI systems.

---

## Conclusion
Using the TOPSIS multi-criteria decision-making approach, DialoGPT was identified as the most suitable pre-trained conversational model under the selected criteria and weights. The study demonstrates how decision-making techniques can be effectively applied to model selection problems in machine learning.

---

## Repository Structure



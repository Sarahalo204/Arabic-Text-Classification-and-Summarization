# Arabic Text Classification and Summarization

This project focuses on processing Arabic text using Natural Language Processing (NLP) techniques. It tackles two main tasks:

1. **Text Classification** – Categorizing Arabic text into factual categories.
2. **Text Summarization** – Generating concise summaries of longer text documents.

---

## Dataset

We used the **AraFacts dataset**, the first large Arabic dataset of naturally occurring claims collected from 5 Arabic fact-checking websites (e.g., Fatabyyano and Misbar) covering claims since 2016. It includes claim text, labels, and metadata useful for research and model development.

---

## Approach

The project explores both **traditional machine learning methods** and **modern deep learning/transformer-based techniques** to evaluate their effectiveness in Arabic NLP. Comparative analysis was conducted to understand the strengths and limitations of different approaches.

---

## Key Findings

- Traditional methods provided reliable baseline performance.
- Transformer-based models captured deeper context but required careful handling of class imbalances.
- Summarization methods varied in keyword accuracy and language coherence, highlighting trade-offs between different approaches.

---

## Classification Analysis

### **Key Observations**

- **SVM**: Highest overall accuracy and balanced performance for major classes, but struggles with underrepresented classes (True, Sarcasm, Unverifiable).  
- **CNN**: Comparable to SVM in accuracy; slightly weaker on low-resource classes, but generalizes reasonably well.  
- **AraBERT**: Excellent recall for the "False" class, but poor performance on other classes due to overfitting; lowest macro and weighted F1.

**Conclusion**
| Best Overall Performance       | **SVM**                   |
| ------------------------------ | ------------------------- |
| Best for Single Dominant Class | **AraBERT (False class)** |
| Best Balanced Performance      | **CNN (Close to SVM)**    |

---

## Summarization Analysis

### Performance Comparison Across Methods
| **Method**      | **Keyword Overlap** | **ROUGE-1 F1** | **BLEU** | **Fluency/Coherence** | **Conciseness** |
|-----------------|------------------|----------------|----------|----------------------|----------------|
| **TF-IDF**      | Best at keywords | N/A            | N/A      | Moderate             | Moderate       |
| **LSTM**        | Moderate         | Highest        | Low      | Low                  | Moderate       |
| **mT5**         | Poor             | Moderate       | Highest  | High                 | Low            |

**Key Observations**
- TF-IDF: Best for retaining keywords but poor abstraction.
- LSTM: High content relevance but repetitive and less readable.
- mT5: Best linguistic quality but worst keyword alignment.

---

### Method-Specific Improvements
| **Method** | **Weakness**              | **Solution**                              |
|------------|---------------------------|------------------------------------------|
| TF-IDF     | Ignores semantics         | Add post-processing (e.g., coreference resolution) |
| LSTM       | Repetitive output         | Incorporate attention mechanisms         |
| mT5        | Poor keyword alignment    | Fine-tune on domain-specific summaries   |

---

## Future Work

- Expand to larger and more diverse Arabic datasets.
- Explore advanced transformer models specialized for Arabic (e.g., AraT5, Noor).
- Investigate multimodal approaches combining text with other data types.


### **Team members:**
- kady Alsaif
- Sarah Alowjan
- Aryaf Alotaibi


### **References:**

[1] Z. S. Ali, W. Mansour, T. Elsayed, and A. Al-Ali, “AraFacts: The First Large Arabic Dataset of Naturally-Occurring Professionally-Verified Claims,” in Proceedings of the Sixth Arabic Natural Language Processing Workshop, Association for Computational Linguistics, 2021.

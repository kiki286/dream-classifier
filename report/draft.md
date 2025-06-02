# 🧠 Dream Clustering: Discovering Emergent Themes in Dream Reports

## 1. Introduction

Dreams have fascinated both scientists and storytellers for their emotional intensity, symbolic imagery, and mysterious logic. This project explores whether unsupervised machine learning — particularly clustering — can reveal emergent dream types based solely on the text of dream reports.

Using dream collections from DreamBank, I aim to:

- Preprocess and vectorize raw dream texts
- Apply clustering techniques to group similar dreams
- Interpret and analyze the resulting clusters
- Visualize and reflect on what the emergent structures reveal
---

## 2. Dataset and Preprocessing

### 2.1 Source and Format

The dreams used in this project were sourced from [DreamBank.net](http://www.dreambank.net), a publicly available repository of dream reports collected for psychological research. Dreams are grouped into individual collections, each stored as a separate JSON file. Each file contains metadata about the dreamer and a list of dreams, each with a unique number, date ("head" field), and a free-text content field.

I used the open-source scraper [DreamScrape](https://github.com/mattbierner/DreamScrape) by Matt Bierner to automate collection of the raw dream files. This provided hundreds of structured dream collections with varying levels of metadata completeness.

### 2.2 Flattening and Standardization
The JSON structure was normalized into a single flat CSV format:
- One row per dream
- Fields include `dream_id`, `dreamer`, `description`, `date_raw`, `content`
- A unique `dream_id` was generated using the dreamer's name and the dream number

This flattening step allowed the dreams to be processed uniformly regardless of original collection.

### 2.3 Text Cleaning

The `content` field of each dream was cleaned using simple heuristics:
- Removal of line breaks, tabs, and excessive whitespace
- Normalization of spacing and quotes
- Retention of original spelling, punctuation, and grammar for interpretability

A cleaned version of each dream was saved to a new column, `text_clean`, to be used in later vectorization steps.

### 2.4 Date Parsing and Correction

The raw `head` date field varied widely in format, ranging from ISO-style `1971-01-01` to partial forms like `07/??/80`. To standardize:
- A flexible date parser was built using `dateutil.parser` with fuzzy logic
- Custom logic was added to interpret two-digit years (e.g., `80`) as belonging to the 1900s, unless clearly in the 2000s
- Invalid or unknown dates were parsed as `NaT` and retained for context


### 2.5 Metadata Limitations

Dream metadata such as age, gender, or dream group was inconsistently present or entirely missing in many files. While some descriptions (e.g., "Ed: dreams of his late wife") hint at gender or context, no structured fields exist for most demographic information. As such, the current analysis focuses solely on dream content, though future work could incorporate heuristic gender labeling or infer context from dreamer groupings.

### 2.6 Output

The final processed dataset consists of 22416 dreams with:
- Cleaned text
- Parsed (or estimated) dates
- Consistent formatting for downstream feature extraction and clustering

This cleaned dataset was saved to `data/processed/cleaned_dreams.csv` and forms the foundation for all subsequent stages of the project.

---

## 3. Feature Extraction

---

## 4. Clustering and Dimensionality Reduction

I applied several clustering methods:
---

## 5. Cluster Interpretation

---

## 6. Visualizations

I included:

## 7. Reflections and Limitations


---

## 8. Conclusion



---

## 9. References

- Domhoff, G. W., & Schneider, A. (2008). Studying dream content using the Hall and Van de Castle coding system and DreamBank.net.
- [DreamBank.net](http://www.dreambank.net/)
[1] Matt Bierner, *DreamScrape*, GitHub repository, https://github.com/mattbierner/DreamScrape
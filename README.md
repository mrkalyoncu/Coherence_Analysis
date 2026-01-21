# Turkish Text Coherence Analysis

A comprehensive toolkit for measuring text coherence in Turkish using multiple NLP methods. This project calculates coherence scores by measuring cosine similarity between adjacent sentences using different embedding techniques.

## 📁 Project Structure

```
coherence_analysis/
├── README.md
├── Text_Excel.xlsx           # Sample data file
├── zemberek-full.jar         # Zemberek NLP library
│
├── bert/                     # 01 - BERT Method
│   ├── 01_BERT_Coherence.ipynb
│   ├── requirements.txt
│   ├── Text_Excel.xlsx
│   └── zemberek-full.jar
│
├── fasttext/                 # 02 - FastText Method
│   ├── 02_FastText_Coherence.ipynb
│   ├── requirements.txt
│   ├── Text_Excel.xlsx
│   └── zemberek-full.jar
│
├── multilm/                  # 03 - MultiLM Method
│   ├── 03_MultiLM_Coherence.ipynb
│   ├── requirements.txt
│   ├── Text_Excel.xlsx
│   └── zemberek-full.jar
│
└── tfidf/                    # 04 - TF-IDF Method
    ├── 04_TF_IDF_Coherence.ipynb
    ├── requirements.txt
    ├── Text_Excel.xlsx
    └── zemberek-full.jar
```

## 🚀 Running on Google Colab

### Step 1: Open the Notebook
1. Navigate to the desired method folder (bert, fasttext, multilm, or tfidf)
2. Open the `.ipynb` file in Google Colab:
   - From GitHub: `File → Open notebook → GitHub` and paste the repo URL
   - Local: `File → Upload notebook` to upload the file

### Step 2: Upload Required Files
After opening the notebook in Colab, upload these files to the files panel on the left:
- `requirements.txt` - Required Python packages
- `Text_Excel.xlsx` - Excel file containing texts to analyze
- `zemberek-full.jar` - Zemberek NLP library for Turkish

### Step 3: Run All Cells
1. Click `Runtime → Run all` or use the shortcut `Ctrl+F9`
2. Wait for all cells to complete execution
3. Results will be displayed on screen and saved as an Excel file

### Step 4: Download Results
Once processing is complete, download the output Excel file from the files panel:
- `bert_coherence_results.xlsx`
- `fasttext_coherence_results.xlsx`
- `multilm_coherence_results.xlsx`
- `tfidf_coherence_results.xlsx`

## 📊 Methods

| No | Method | Model | Description |
|----|--------|-------|-------------|
| 01 | BERT | dbmdz/bert-base-turkish-cased | Uses CLS token embeddings |
| 02 | FastText | cc.tr.300.bin | Averages word vectors |
| 03 | MultiLM | paraphrase-multilingual-MiniLM-L12-v2 | Sentence transformer embeddings |
| 04 | TF-IDF | sklearn TfidfVectorizer | Term frequency-inverse document frequency |

## 📝 Text Variants

Each method calculates coherence scores for the following 4 text variants:

1. **Raw** - Original sentences
2. **Cleaned** - Punctuation removed, converted to lowercase
3. **Stemmed** - Morphological stemming applied using Zemberek
4. **Cleaned + Stemmed** - Both cleaning and stemming applied

## ⚙️ Notebook Structure

All notebooks follow the same structure:

1. **Setup and Installation** - Package installation and file paths
2. **Initialize Zemberek and Model** - JVM and model loading
3. **Preprocessing Functions** - Sentence extraction, cleaning, stemming
4. **Coherence Calculation** - Cosine similarity computation
5. **Load Data and Process** - Data loading and processing loop
6. **Save Results** - Display results and save to Excel

## 📋 Requirements

Specified in the `requirements.txt` file in each folder. General requirements:
- `jpype1` - Java-Python bridge (for Zemberek)
- `pandas` - Data processing
- `numpy` - Numerical operations
- `openpyxl` - Excel read/write
- Model-specific libraries (transformers, fasttext, sentence-transformers, scikit-learn)

## 🔧 Technologies Used

- **Zemberek NLP** - Turkish natural language processing library for sentence extraction and morphological analysis
- **HuggingFace Transformers** - For BERT model
- **Sentence Transformers** - For MultiLM model
- **FastText** - Facebook's word embedding library
- **Scikit-learn** - For TF-IDF vectorization

## 📄 License

This project is licensed under the Apache License 2.0.

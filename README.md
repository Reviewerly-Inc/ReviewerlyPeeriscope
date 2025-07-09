# PeeriScope

A modular FastAPI-based API to automatically analyze scientific paper reviews. The system extracts multiple review quality signals using multiple pretrained models.

---

## API Explanation
ONE LINE EXPLAIN IT HAS 2 MODES AND WHAT IT IS

## Launch the API
```bash
uvicorn app.main:app --reload
```

Visit: [http://localhost:8000/docs](http://localhost:8000/docs) for interactive API documentation.

---


## API Example Request - Manual Mode
```json
{
  "title": "Paper Title",
  "abstract": "Paper abstract here...",
  "review": "The methodology is sound. However, see Figure 3. Is the experiment reproducible?"
}
```

## API Example Response - Manual Mode
```json
{
  "title": "Paper Title",
  "abstract": "Paper abstract here...",
  "review": "The methodology is sound. However, see Figure 3. Is the experiment reproducible?"
}
```

## API Example Request - OpenReview
```json
{
  "title": "Paper Title",
  "abstract": "Paper abstract here...",
  "review": "The methodology is sound. However, see Figure 3. Is the experiment reproducible?"
}
```

## API Example Response - OpenReview
```json
{
  "title": "Paper Title",
  "abstract": "Paper abstract here...",
  "review": "The methodology is sound. However, see Figure 3. Is the experiment reproducible?"
}
```





## 🚀 Quick Start

## Features
* ✅ **MATTR (Lexical Diversity)** — using `taaled` and `pylats`
* ✅ **Sentiment Polarity** — using `TextBlob`
* ✅ **Politeness Score** — using `xlm-roberta-large-tydip`
* ✅ **Question Count** — using `bert-mini-finetune-question-detection`
* ✅ **Citation Count** — using regex-based citation detection
* ✅ **Semantic Similarity** — using `allenai/specter`
* ✅ **Readability Score** — using `textstat` (Flesch Reading Ease)
* ✅ **Hedging Labels** — using `jeniakim/hedgehog` model
* ✅ **Explicit References** — detecting "section", "figure", etc.


## Expert Annotated Dataset
In this section, we provide detailed instructions on how to download the dataset and a sample of the raw data.

### How to Download the Data
Note: You need to install the gdown package to download the dataset.
```bash
pip install gdown
```

If you already have the gdown package installed, you can use the following commands to download the dataset:
```bash
cd human-annotation-data/
gdown --folder https://drive.google.com/drive/folders/14zWD3G_z_1gXDLEAkI7lz3KK3NHkAH8w?usp=sharing
```

### Sample of the Raw Data
Here's a sample data from Expert Annotated Dataset.
```json
{
    "paper_id": "120",
    "submitted_at": "2025-05-16T14:44:27.215679",
    "metrics": {
        "review_Peter-W.-Glynn_Comprehensiveness": 1,
        "review_Peter-W.-Glynn_Usage_of_Technical_Terms": 4,
        "review_Peter-W.-Glynn_Factuality": "partially factual",
        "review_Peter-W.-Glynn_Sentiment_Polarity": "neutral",
        "review_Peter-W.-Glynn_Politeness": "polite",
        "review_Peter-W.-Glynn_Vagueness": "moderate",
        "review_Peter-W.-Glynn_Objectivity": 3,
        "review_Peter-W.-Glynn_Fairness": 3,
        "review_Peter-W.-Glynn_Actionability": 4,
        "review_Peter-W.-Glynn_Constructiveness": 4,
        "review_Peter-W.-Glynn_Relevance_Alignment": 3,
        "review_Peter-W.-Glynn_Clarity_and_Readability": 4,
        "review_Peter-W.-Glynn_Overall_Quality": 70,
        "review_Ciemon-Frank-Caballes_Comprehensiveness": 0,
        "review_Ciemon-Frank-Caballes_Usage_of_Technical_Terms": 4,
        "review_Ciemon-Frank-Caballes_Factuality": "unfactual",
        "review_Ciemon-Frank-Caballes_Sentiment_Polarity": "neutral",
        "review_Ciemon-Frank-Caballes_Politeness": "polite",
        "review_Ciemon-Frank-Caballes_Vagueness": "high",
        "review_Ciemon-Frank-Caballes_Objectivity": 2,
        "review_Ciemon-Frank-Caballes_Fairness": 3,
        "review_Ciemon-Frank-Caballes_Actionability": 1,
        "review_Ciemon-Frank-Caballes_Constructiveness": 1,
        "review_Ciemon-Frank-Caballes_Relevance_Alignment": 2,
        "review_Ciemon-Frank-Caballes_Clarity_and_Readability": 3,
        "review_Ciemon-Frank-Caballes_Overall_Quality": 2
    }
}
```


## 📄 License
TBD

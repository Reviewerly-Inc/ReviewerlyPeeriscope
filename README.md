# ReviewerlyMonitor

A modular FastAPI-based API to automatically analyze scientific paper reviews.
The system extracts multiple review quality signals using multiple pretrained models.

---

## ✨ Features

* ✅ **MATTR (Lexical Diversity)** — using `taaled` and `pylats`
* ✅ **Sentiment Polarity** — using `TextBlob`
* ✅ **Politeness Score** — using `xlm-roberta-large-tydip`
* ✅ **Question Count** — using `bert-mini-finetune-question-detection`
* ✅ **Citation Count** — using regex-based citation detection
* ✅ **Semantic Similarity** — using `allenai/specter`
* ✅ **Readability Score** — using `textstat` (Flesch Reading Ease)
* ✅ **Hedging Labels** — using `jeniakim/hedgehog` model
* ✅ **Explicit References** — detecting "section", "figure", etc.

---

## 🚀 Quick Start

### 1️⃣ Clone and Setup

```bash
git clone https://github.com/Reviewerly-Inc/ReviewerlyMonitor.git
cd ReviewerlyMonitor
python3 -m venv venv
source venv/bin/activate
```

### 2️⃣ Install Dependencies

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

### 3️⃣ Launch the API

```bash
uvicorn app.main:app --reload
```

Visit: [http://localhost:8000/docs](http://localhost:8000/docs) for interactive API documentation.

---

## ⚠ Notes

* Ensure you have enough RAM/GPU for models like **HEDGEhog**, **Specter**, and **Politeness (XLM-RoBERTa)**.
* All models are automatically downloaded on first run.

---

## 🔧 Optional Optimizations

* GPU acceleration automatically used if available (`torch.cuda.is_available()`).
* All models are loaded globally for efficient inference.
* Model preloading optimization in progress (coming soon).

---

## 📂 Project Structure

```bash
RottenReviewsAPI/
  ├── app/
  │   ├── analyzer.py
  │   ├── main.py
  │   ├── models.py
  │   └── services/
  │       ├── mattr.py
  │       ├── sentiment.py
  │       ├── politeness.py
  │       ├── questions.py
  │       ├── citations.py
  │       ├── similarity.py
  │       ├── readability.py
  │       ├── hedging.py
  │       └── explicit_references.py
  └── requirements.txt
  └── README.md
```

---

## ✅ API Example Request

```json
{
  "title": "Paper Title",
  "abstract": "Paper abstract here...",
  "review": "The methodology is sound. However, see Figure 3. Is the experiment reproducible?"
}
```

---

## 📄 License

I have no right to to fill this section yet, but I will add it soon.

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
  "review": "string",
  "title": "string",
  "abstract": "string",
  "reviewer_openalex_id": "string",
  "reviewer_name": "string"
}
```

## API Example Response - Manual Mode
```json
{
  "review_length": 0,
  "mattr_score": 0,
  "question_count": 0,
  "citation_count": 0,
  "sentiment_score": 0,
  "politeness_score": 0,
  "similarity_score": 0,
  "readability_score": 0,
  "hedging_score": 0,
  "explicit_reference_count": 0,
  "reviewer_openalex_id": "string",
  "reviewer_name": "string",
  "reviewer_citation_count": 0,
  "reviewer_h_index": 0,
  "reviewer_academic_career_length": 0,
  "general_alignment": 0,
  "in_depth_alignment": 0,
  "recency_alignment": 0,
  "predicted_overall_quality_score": 0
}
```

## API Example Request - Manual Mode LLM
```json
{
  "review": "string",
  "title": "string",
  "abstract": "string",
  "reviewer_openalex_id": "string",
  "reviewer_name": "string"
}
```

## API Example Response - Manual Mode LLM
```json
{
  "comprehensiveness": 0,
  "usage_of_technical_terms": 0,
  "factuality": "string",
  "sentiment_polarity": "string",
  "politeness": "string",
  "vagueness": "string",
  "objectivity": 0,
  "fairness": 0,
  "actionability": 0,
  "constructiveness": 0,
  "relevance_alignment": 0,
  "clarity_and_readability": 0,
  "overall_quality": 0
}
```


## API Example Request - OpenReview
```json
{
  "url": "string"
}
```

## API Example Response - OpenReview
```json
{
  "analysis_results": [
    {
      "quantifiable_analysis": {
        "review_length": 0,
        "mattr_score": 0,
        "question_count": 0,
        "citation_count": 0,
        "sentiment_score": 0,
        "politeness_score": 0,
        "similarity_score": 0,
        "readability_score": 0,
        "hedging_score": 0,
        "explicit_reference_count": 0,
        "reviewer_openalex_id": "string",
        "reviewer_name": "string",
        "reviewer_citation_count": 0,
        "reviewer_h_index": 0,
        "reviewer_academic_career_length": 0,
        "general_alignment": 0,
        "in_depth_alignment": 0,
        "recency_alignment": 0,
        "predicted_overall_quality_score": 0
      },
      "llm_analysis": {
        "comprehensiveness": 0,
        "usage_of_technical_terms": 0,
        "factuality": "string",
        "sentiment_polarity": "string",
        "politeness": "string",
        "vagueness": "string",
        "objectivity": 0,
        "fairness": 0,
        "actionability": 0,
        "constructiveness": 0,
        "relevance_alignment": 0,
        "clarity_and_readability": 0,
        "overall_quality": 0
      },
      "review_text": "string",
      "reviewer_name": "string"
    }
  ],
  "paper_title": "string",
  "paper_abstract": "string"
}
```

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


## License
TBD

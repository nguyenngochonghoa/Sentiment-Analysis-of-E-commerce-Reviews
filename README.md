# Sentiment-analysis-of-customer-comments-using-deep-learning-model

## 📌 Project Overview
This project focuses on **Aspect-Based Sentiment Analysis (ABSA)** for product reviews collected from **Tiki.vn**.  
The goal is to identify sentiments (positive, negative, neutral) toward different aspects of e-commerce products (e.g., quality, price, delivery, service).  

By fine-tuning the **PhoBERT** model on an annotated dataset, this research provides insights into customer opinions that go beyond overall ratings, enabling businesses to better understand customer needs and improve services.

---

## Dataset
- **Source**: Product reviews scraped from Tiki.vn.  
- **Annotation**: Sentiment labels were generated using ChatGPT API with human verification.  
- **Size**: ~X,XXX reviews (multi-aspect, multi-sentiment).  
- **Format**: Structured in CSV with fields for review text, aspect, and sentiment.  

---

## Methodology
The workflow consists of the following steps:

1. **Data Collection**  
   - Extract product links and reviews from Tiki.vn.  
   - Save raw comments for further processing.  

2. **Data Preprocessing**  
   - Cleaning text (lowercasing, removing special characters, tokenization).  
   - Normalizing Vietnamese text for PhoBERT input.  

3. **Data Labeling**  
   - Aspect–sentiment pairs generated via ChatGPT API.  
   - Manual checking to ensure labeling quality.  

4. **Model Training**  
   - Fine-tune **PhoBERT** on labeled dataset.  
   - Training on Google Colab GPU with PyTorch/Transformers.  

5. **Evaluation**  
   - Metrics: Accuracy, Precision, Recall, F1-score.  
   - Comparison across aspects and sentiment classes.  

---

## Results
- **Overall performance**:  
  - Accuracy: ~89.7%  
  - The model shows stable results across 5-fold stratified cross-validation, indicating good generalization.  

- **By sentiment class**:  
  - **Neutral/Irrelevant**: Highest performance, F1 ≈ 0.93 → model is strong at filtering out non-relevant aspects.  
  - **Positive**: Good performance, F1 ≈ 0.87 → captures positive expressions in Vietnamese reviews well.  
  - **Negative**: Lower performance, F1 ≈ 0.78 → still acceptable but affected by fewer samples and complex expressions.  

- **By aspect**:  
  - Strong performance in frequent aspects such as **Delivery, Price, Packaging** (Positive F1 > 0.94).  
  - Moderate results in **Quality and Appearance** — positive detection is reliable, but negative sentiment is harder to capture.  
  - Lower results in **General Evaluation** and **Other aspects**, mainly due to imbalanced data and vague/mixed content.  

- **Key insights**:  
  - The model works best when aspects are clearly defined and well-represented in training data.  
  - Performance drops for underrepresented aspects or ambiguous/multi-aspect comments.

---

## Practical Applications
- Support businesses in **customer feedback analysis**.  
- Identify **specific strengths and weaknesses** of products/services.  
- Provide input for **business intelligence and decision-making**.  

---

## Limitations & Future Work
- **Data imbalance** across aspects led to uneven model performance.  
- **Sarcasm, mixed sentiments** remain challenging for the model.  
- Future improvements:  
  - Expanding dataset to more diverse products.  
  - Applying advanced labeling strategies.  
  - Exploring large language models (LLMs) for better aspect extraction.  


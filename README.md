# Hi, I'm Kerem

Linguistics graduate from Boğaziçi University, currently working as an AI/LLM evaluator at Yandex with a focus on NLP and machine learning engineering.

## Projects

### [Named Entity Recognition with DistilBERT](https://github.com/cliteka-cell/ner-wikiann) · [Live Demo](https://huggingface.co/spaces/Reshiman/ner-wikiann)
Fine-tuned DistilBERT on WikiANN English (20k sentences) for named entity recognition. Reached an F1 score of 0.82 across PER, ORG, and LOC entities. Manually checked 80k test tokens for errors and found that 74% were misclassifications rather than missed detections—mostly confusing LOC and ORG because of ambiguous names. Also noticed that some model predictions actually made more sense than the original dataset labels. Deployed as an interactive HuggingFace Space.
`Python` `HuggingFace` `DistilBERT` `PyTorch` `Gradio`

### [Stance Detection with DistilBERT](https://github.com/cliteka-cell/stance-detection) · [Live Demo](https://huggingface.co/spaces/Reshiman/stance-detection)
Fine-tuned DistilBERT on the IBM Argument Quality dataset (30k arguments) to classify debate arguments as PRO or CON. Reached an F1 score of 0.90 on a perfectly balanced dataset. The project also looks into stance ambiguity and how the model handles tricky argumentative language.
`Python` `HuggingFace` `DistilBERT` `PyTorch` `Gradio`

### [Cross-Lingual Transfer: Turkish Sentiment Analysis](https://github.com/cliteka-cell/turkish-sentiment-crosslingual) · [Live Demo](https://huggingface.co/spaces/Reshiman/turkish-sentiment-mbert)
Cross-lingual transfer experiment testing an English sentiment model on Turkish — scored 41.7% accuracy (worse than random). Fine-tuned mBERT on 4,486 Turkish restaurant reviews, recovering to 84.4% accuracy (+42.6% gain). Includes analysis of Turkish morphology, tokenization failure modes, and within-language domain mismatch.
`Python` `HuggingFace` `mBERT` `PyTorch` `Gradio` `Turkish NLP`

### [ALES Oracle — AI Exam Prep Tool · Click for Live Website](https://ales-oracle.streamlit.app/#ales-oracle)
Topic-based question generator for the Turkish ALES exam. It pulls from a database of 1,400+ real past questions to generate practice questions and step-by-step solutions using Gemini 2.5 Flash and Gemini 3.0. Also includes study formula cards based on the most common question types in past exams.
`Python` `Streamlit` `Gemini 2.5 Flash` `Pandas`

### [ARMAS — Algorithmic S&P EA](https://github.com/cliteka-cell/ARMAS_Project_Full)
Mean-reversion algorithmic trading bot for MetaTrader 5 using an EWM band strategy. Took it from a basic Python backtest to a live MT5 Expert Advisor over 18 versions. Uses RSI, ATR, and slope filters, along with Optuna for parameter tuning and ML training data generated from live trades.
`Python` `MQL5` `Optuna`

### [İzmir Acil — Emergency Service Finder · Click for Live Website](https://izmir-acil.streamlit.app/)
A web app that helps people find over 4,600 verified emergency services in İzmir. Uses an "Open Now" feature that checks current local time against store hours, and sorts results by distance using browser GPS. Built a mobile-friendly map interface with quick buttons for WhatsApp, calling, and Google Maps directions.
`Python` `Streamlit` `SQLite` `Folium` `Geopy`

### [House Price Prediction](https://github.com/cliteka-cell/House_Price_Prediction)
Regression model on the Ames Housing Dataset. Compared Linear Regression, Ridge, Random Forest, and XGBoost. Handled feature engineering (TotalSF, TotalBaths, HouseAge) and log target transformation. XGBoost performed best with an R² of 0.944 and a $21,224 RMSE.
`Python` `Scikit-learn` `XGBoost`

### [E-Commerce Customer Behavior Analysis](https://github.com/cliteka-cell/E-Commerce-Analysis)
Analyzed 540k transactions for a UK gift retailer. Handled EDA, Pareto analysis, and RFM customer segmentation (Champions, At-Risk, Lost), plus a cohort retention heatmap. Main takeaway: the top 26% of customers brought in 80% of the revenue.
`Python` `Pandas` `Seaborn`

---

## Skills

**Languages:** Python · SQL · C# · Pine Script  

**Data:** Pandas · Matplotlib · Seaborn · EDA · Statistical Analysis · Geospatial Analysis (Folium/Geopy)

**ML:** Scikit-learn · XGBoost · Feature Engineering · Model Evaluation · Fine-tuning Transformers (HuggingFace) · NER · Token Classification

**Finance:** Algorithmic Trading · Backtesting · Order Flow · MetaTrader 5  

**Other:** NLP · LLM Evaluation · Intermediate Excel · Web App Deployment (Streamlit) · Web Scraping

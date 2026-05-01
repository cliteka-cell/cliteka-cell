# Hi, I'm Kerem

Linguistics graduate from Boğaziçi University, currently working as an AI/LLM evaluator at Yandex with a focus on NLP and machine learning engineering.

## Projects

### [Named Entity Recognition with DistilBERT](https://github.com/cliteka-cell/ner-wikiann) · [Live Demo](https://huggingface.co/spaces/Reshiman/ner-wikiann)
Fine-tuned DistilBERT on WikiANN English (20k sentences) for named entity recognition. Achieved F1=0.82 across PER, ORG, and LOC entity types. Conducted full error analysis on 80k test tokens — identified that 74% of errors are misclassifications rather than missed detections, with LOC↔ORG confusion (1,279 cases) as the dominant failure mode driven by geopolitical ambiguity. Discovered cases where model predictions are more linguistically defensible than the ground truth labels, revealing annotation inconsistencies in the dataset. Deployed as an interactive demo on HuggingFace Spaces.
`Python` `HuggingFace` `DistilBERT` `PyTorch` `Gradio`

### [Stance Detection with DistilBERT](https://github.com/cliteka-cell/stance-detection) · [Live Demo](https://huggingface.co/spaces/Reshiman/stance-detection)
Fine-tuned DistilBERT on the IBM Argument Quality dataset (30k arguments) to classify whether an argument is PRO or CON on a given debate topic. Achieved F1=0.90 on a perfectly balanced dataset. Includes linguistic analysis of stance ambiguity, confidence calibration, and the pragmatic nature of argumentative language.
`Python` `HuggingFace` `DistilBERT` `PyTorch` `Gradio`

### [ALES Oracle — AI Exam Prep Tool · Click for Live Website](https://ales-oracle.streamlit.app/#ales-oracle)
Topic-based question generator for the Turkish ALES graduate entrance exam. Analyzes a database of 1,400+ real exam questions across 13 sittings to generate difficulty-calibrated practice questions and step-by-step solutions using Gemini 2.5 Flash and Gemini 3.0. Features a per-topic formula card system built from frequency analysis of real exam data.
`Python` `Streamlit` `Gemini 2.5 Flash` `Pandas`

### [ARMAS — Algorithmic S&P EA](https://github.com/cliteka-cell/ARMAS_Project_Full)
Mean-reversion Expert Advisor for MetaTrader 5 built on EWM band strategy. Developed from a Python backtest into a production-ready MT5 EA across 18 versions, with RSI/ATR/slope signal filters, Optuna-based parameter optimization, and ML training data generated from live trade logs.
`Python` `MQL5` `Optuna`

### [İzmir Acil — Hyperlocal Emergency Service Finder · Click for Live Website](https://izmir-acil.streamlit.app/)
Hyperlocal web application providing real-time access to 4,600+ verified emergency service providers in İzmir. Features an automated "Open Now" engine that parses dynamic weekly operating hours against local time, browser-based GPS for proximity-based sorting, and an interactive Folium geospatial interface. Engineered a mobile-optimized UX with collapsible mapping and integrated direct-action triggers for WhatsApp, telephony, and Google Maps navigation.
`Python` `Streamlit` `SQLite` `Folium` `Geopy`

### [House Price Prediction](https://github.com/cliteka-cell/House_Price_Prediction)
Regression project on the Ames Housing Dataset comparing Linear Regression, Ridge, Random Forest, and XGBoost. Includes feature engineering (TotalSF, TotalBaths, HouseAge), log target transformation, and cross-validated evaluation. XGBoost achieved R²=0.944 and RMSE=$21,224.
`Python` `Scikit-learn` `XGBoost`

### [E-Commerce Customer Behavior Analysis](https://github.com/cliteka-cell/E-Commerce-Analysis)
End-to-end analysis of 540k transactions from a UK wholesale gift retailer. Covers EDA, Pareto analysis, RFM customer segmentation (Champions, At-Risk, Lost), and cohort retention heatmap. Key finding: top 26% of customers drive 80% of revenue.
`Python` `Pandas` `Seaborn`

---

## Skills

**Languages:** Python · SQL · C# · Pine Script  

**Data:** Pandas · Matplotlib · Seaborn · EDA · Statistical Analysis · Geospatial Analysis (Folium/Geopy)

**ML:** Scikit-learn · XGBoost · Feature Engineering · Model Evaluation · Fine-tuning Transformers (HuggingFace) · NER · Token Classification

**Finance:** Algorithmic Trading · Backtesting · Order Flow · MetaTrader 5  

**Other:** NLP · LLM Evaluation · Intermediate Excel · Web App Deployment (Streamlit) · Web Scraping

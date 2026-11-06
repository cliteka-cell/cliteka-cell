# Hi, I'm Kerem

Linguistics graduate from Boğaziçi University, previously an AI/LLM evaluator through Gini Talent (the end client is under NDA), with a focus on NLP and machine learning engineering.

🌐 **Portfolio:** [kerem.confluencearray.com](https://kerem.confluencearray.com)

## Projects

### [Zero-Shot Multilingual NER](https://github.com/cliteka-cell/zero-shot-multilingual-ner)
Cross-lingual NER transfer to Turkish, German, and Arabic using no target-language labels at all. XLM-RoBERTa backbone with a contrastive alignment objective (InfoNCE on real OPUS-100 parallel sentences) plus CoSDA-ML code-switching augmentation via MUSE bilingual lexicons. Built as a full research study rather than a single run: a 5-config ablation, multi-seed variance runs, a translate-train baseline, a few-shot curve, and token and entity level alignment analyses. The ablation refutes the project's own thesis - plain full fine-tuning beats the contrastive pipeline on German (0.753 vs 0.744) and Arabic (0.495 vs 0.456), so the contrastive objective is reported as not helping rather than quietly dropped. A follow-up hypothesis about entity-type alignment was tested directly and also came back refuted. Written up in PAPER.md with a full development log.
`Python` `PyTorch` `XLM-RoBERTa` `Contrastive Learning` `InfoNCE` `Zero-Shot Transfer` `seqeval`

### [Named Entity Recognition with DistilBERT](https://github.com/cliteka-cell/ner-wikiann) · [Live Demo](https://huggingface.co/spaces/Reshiman/ner-wikiann)
Fine-tuned DistilBERT on WikiANN English (20k sentences) for named entity recognition. Reached an F1 score of 0.82 across PER, ORG, and LOC entities. Manually checked 80k test tokens for errors and found that 74% were misclassifications rather than missed detections-mostly confusing LOC and ORG because of ambiguous names. Also noticed that some model predictions actually made more sense than the original dataset labels. Deployed as an interactive HuggingFace Space.
`Python` `HuggingFace` `DistilBERT` `PyTorch` `Gradio`

### [Stance Detection with DistilBERT](https://github.com/cliteka-cell/stance-detection) · [Live Demo](https://huggingface.co/spaces/Reshiman/stance-detection)
Fine-tuned DistilBERT on the IBM Argument Quality dataset (30k arguments) to classify debate arguments as PRO or CON. Reached an F1 score of 0.90 on a perfectly balanced dataset. The project also looks into stance ambiguity and how the model handles tricky argumentative language.
`Python` `HuggingFace` `DistilBERT` `PyTorch` `Gradio`

### [Turkish NLP Benchmark](https://github.com/cliteka-cell/turkish-nlp-benchmark) · [Live Demo](https://huggingface.co/spaces/Reshiman/turkish-nlp-benchmark)
Three-way benchmark comparing English DistilBERT (zero-shot), mBERT (multilingual), and BERTurk (Turkish-only) on Turkish sentiment analysis. Zero-shot scored 41.7% (worse than random), mBERT recovered to 84.4%, BERTurk reached 94.3% - a +9.95% gain over multilingual on identical training. Interactive demo lets users test all three models in real time.
`Python` `HuggingFace` `mBERT` `BERTurk` `PyTorch` `Gradio` `Turkish NLP`

### [ALES Oracle: AI Exam Prep Tool · Click for Live Website](https://ales-oracle.streamlit.app/#ales-oracle)
Topic-based question generator for the Turkish ALES exam. It pulls from a database of 1,400+ real past questions to generate practice questions and step-by-step solutions using Gemini 2.5 Flash and Gemini 3.0. Also includes study formula cards based on the most common question types in past exams.
`Python` `Streamlit` `Gemini 2.5 Flash` `Pandas`

### [AI Investor: Local LLM Research System](https://cliteka-cell.github.io/ai-investor-dashboard/) · [Writeup](https://github.com/cliteka-cell/ai-investor-writeup)
Self-hosted investment research system running entirely on local hardware, no external LLM API. Research only by design: it never places a trade, and the broker API keys are deliberately left empty. A three-layer screener runs across large-cap, Russell 2000, and crypto tracks: a quantitative momentum pass with no LLM, then a tool-calling web-search gather (Qwen via a self-hosted SearXNG), then a deep thesis and pre-mortem pass (DeepSeek R1 32B). 18 scheduled jobs kept it running unattended, including a living paper portfolio with stop-loss exits, position caps and inverse-volatility sizing, thesis drift detection against each position's original thesis, and a data quality canary that validates the shape of every external API response rather than just its status code. The system grades itself: a calibration job measures forward returns per conviction tier against a track-appropriate passive benchmark (SPY / IWM / BTC). Its last calibration (September 2026, nine weekly archives, so a few months of picks and not a verdict) was not flattering: the high- and medium-conviction tiers of both stock tracks all trailed their benchmarks, for example large-cap high conviction by 6.0 points of alpha over 19 picks and small-cap medium by 8.4 points over 62, while crypto medium conviction roughly matched BTC (+0.7 points over 23). Reported as found. The system has been paused since September 2026, and the public dashboard (linked above) is a snapshot of its last run: the briefing, macro regime, screener conviction tiers, and those calibration numbers, unedited.
`Python` `Ollama` `DeepSeek R1 32B` `Qwen` `Local LLM` `Docker` `SearXNG` `yfinance` `SEC EDGAR`

### [ARMAS: Algorithmic S&P EA](https://github.com/cliteka-cell/ARMAS_Project_Full)
Mean-reversion algorithmic trading bot for MetaTrader 5 using an EWM band strategy. Took it from a basic Python backtest to a live MT5 Expert Advisor over 18 versions. Uses RSI, ATR, and slope filters, along with Optuna for parameter tuning and ML training data generated from live trades.
`Python` `MQL5` `Optuna`

### [ARMAS RL Trading Agent](https://github.com/cliteka-cell/armas-rl)
Reinforcement learning agent for the ARMAS mean-reversion strategy on SP500 futures (1H). Built a hybrid architecture where MaskablePPO learns trade timing while a deterministic state machine handles position scaling, stops, and partial take-profits. Iterated through six reward designs to escape degenerate policies, then ran a signal-vs-friction analysis: signal edge (+0.056% per touch) is smaller than commission friction (~0.2% per trade). Documented as a rigorous negative result.
`Python` `gymnasium` `stable-baselines3` `MaskablePPO` `Pine Script`

### [Confluence Array · Click for Live Website](https://confluencearray.com)
Professional TradingView indicator suite for confluence zone detection. Auto-detects the trading mode (intraday / hourly / macro) and loads the relevant levels - ARMAS adaptive bands, VWAP, FVGs, market profile, open interest signal matrix, CVD divergence, and session tracking. A scoring engine ranks zones by confluence strength.
`Pine Script v6` `TradingView` `HTML` `CSS` `JavaScript` `Canvas API` `SVG`

### TMSCA: Market Structure Confluence Array · Commercial (in development)
Fuses the Confluence Array level engine with a market-structure event engine in one overlay, so that where the levels sit and when a setup fires gate each other. BOS / CHoCH, liquidity sweeps, SFP, and session-CVD divergence are scored and graded A- / A / A+, then filtered by a context gate built from zone bias, ARMAS stretch, and multi-timeframe alignment.
`Pine Script v6` `TradingView` `Smart Money Concepts` `Order Flow` `CVD`

### [Naked POC - Daily](https://github.com/cliteka-cell/npoc-daily)
Open-source TradingView indicator that tracks unvisited daily Points of Control as clean dashed levels. No histogram, no boxes - only the levels that still have magnetic pull on price. Uses a close-weighted triangular volume distribution so the POC lands closer to where price repeatedly settled. Auto-removes filled levels and expires old ones.
`Pine Script v6` `TradingView` `Volume Profile` `Market Profile`

### [Session CVD Divergence](https://github.com/cliteka-cell/session-cvd-divergence)
Splits Cumulative Volume Delta into independent Asian, London, and NY session streams, each resetting at session open. Detects all four divergence types (regular and hidden) between price and order flow using a same-session pivot constraint to prevent false cross-session signals. Two-script setup: CVD pane with divergence lines, plus an overlay that draws matching price pivot lines and labels on the main chart.
`Pine Script v6` `TradingView` `CVD` `Order Flow` `Volume Delta`

### [Auto Anchored VP - True TPO Logic](https://github.com/cliteka-cell/auto-anchored-vp)
Open-source Pine Script replication of TradingView's native Anchored Volume Profile. Uses even TPO distribution across each bar's high-low range and the standard dual-bin Value Area expansion algorithm matching original Steidlmayer methodology. Published as an educational reference for understanding why accurate volume profile calculation is difficult in Pine Script.
`Pine Script v6` `TradingView` `Volume Profile` `TPO` `Value Area`

### [SFP Detector](https://github.com/cliteka-cell/sfp-detector)
Detects swing failure patterns - bars that wick past a prior swing high or low and close back inside it, sweeping the liquidity at that level. Features multi-level sweep detection (SFP / SFP+ / SFP++), ATR-based quality filters, auto pivot length by timeframe, HTF trend filter, session window filter, and retest tracking after each signal.
`Pine Script v6` `TradingView` `Liquidity` `Price Action` `Order Flow`

### [Market Structure (BOS/CHoCH)](https://github.com/cliteka-cell/market-structure) · [TradingView](https://www.tradingview.com/script/0t7puDyH-Market-Structure-BOS-CHOCH-Advanced-Improved/)
Maps market structure as Break of Structure (continuation) and Change of Character (reversal) from a single break engine and trend state, across two layers: a bold swing skeleton with HH/HL/LH/LL and trailing levels, plus a faded internal layer for the legs inside each swing. Unbroken swing highs and lows project as liquidity pools that clear the moment price wicks through them.
`Pine Script v6` `TradingView` `Market Structure` `Liquidity` `Price Action`

### [Trading Journal · Live Preview](https://trading-journal-preview.streamlit.app)
Full-featured trading journal built with Python and Streamlit. Multi-journal support, MT5 report import, pre/post/position analysis with screenshot upload, equity curve, calendar heatmap, analytics by session/hour/day, Hall of Fame, and PDF export. Used in real daily trading.
`Python` `Streamlit` `Pandas` `Plotly` `fpdf`

### Investing Journal: Buy-and-Hold Portfolio Tracker · Private
The sibling app to Trading Journal, rebuilt around long-term holdings instead of in/out trades. Net worth and unrealized/realized gain at a glance, per-ticker average-cost-basis tracking with live price updates, an allocation donut chart, dividend logging, and best/worst performer cards. Same stack as Trading Journal, different discipline: this one tracks what you hold, not what you traded.
`Python` `Streamlit` `Pandas` `Plotly`

### [Peony Nails · Click for Live Website](https://peonynails.store)
Freelance site build for a nail studio, live on a custom domain with real DNS setup, not a template drop-in. Bilingual EN/TR content throughout, per-product detail pages with a photo gallery and lightbox, a custom coverflow carousel for the nail-art gallery, and a Formspree-backed contact form. Real photos, a real service menu, and real client testimonials, sourced directly from the studio owner rather than placeholder content.
`HTML` `CSS` `JavaScript` `Netlify` `Formspree`

### [Voynich: A Private Study Room That Lives on Your Computer](https://cliteka-cell.github.io/voynich-releases/) · [Download](https://github.com/cliteka-cell/voynich-releases)
A study tracker I started as a small language-learning timer, then merged with a second tracker into one app and shipped as a real product. Everything a student or self-learner keeps in five places, in one program that runs on your own PC and opens in your browser: a session timer and log, weekly and long-term goals with a pace to finish on time, several separate rooms (a language, a degree, a hobby), notes that link to each other into a graph, a library with ISBN and DOI lookup and BibTeX and RIS citations, a PDF and EPUB reader with highlights, flashcards, and an optional AI tab that uses a local Ollama model or your own key and never a hosted one. No account, no cloud, daily backups with a preview before restoring, and optional peer-to-peer study circles that need no server. Ships as a Windows installer and a Mac disk image that update themselves with signed updates, with a public site, a getting-started guide, a full manual and terms. Free to use, not open source.
`Next.js` `TypeScript` `Prisma` `SQLite` `Local-First` `Desktop Packaging`

### [İzmir Acil: Emergency Service Finder · Click for Live Website](https://izmir-acil.streamlit.app/)
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

**Languages:** Python · SQL · JavaScript · TypeScript · HTML · CSS · C# · Pine Script v6 · R

**ML & NLP:** Scikit-learn · XGBoost · Feature Engineering · Model Evaluation · Fine-tuning Transformers (HuggingFace) · NER · Token Classification · Cross-lingual & Zero-Shot Transfer · Contrastive Learning (InfoNCE) · Ablation & Multi-Seed Study Design · Reinforcement Learning (PPO) · LLM Evaluation

**LLM Engineering:** Local LLM Deployment (Ollama) · Prompt & Context Engineering · Structured Output · Retrieval & Web-Augmented Agents · Scheduled LLM Pipelines

**Data:** Pandas · Matplotlib · Seaborn · EDA · Statistical Analysis · Geospatial Analysis (Folium/Geopy)

**Web:** Next.js · TypeScript · Prisma · Canvas API · SVG · Streamlit · Gradio · GitHub Pages · Netlify · i18n · Desktop Packaging & Signed Auto-Updates

**Finance:** Algorithmic Trading · Backtesting · Order Flow · Volume Profile · CVD · Market Profile · Liquidity Analysis · MetaTrader 5 · TradingView

**Other:** NLP · Intermediate Excel · Web Scraping

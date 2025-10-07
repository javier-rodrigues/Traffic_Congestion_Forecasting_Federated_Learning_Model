# Meeting Minutes
## Meeting Information
**Meeting Date/Time:** Week 1 

[X] Read articles on Federated Learning

[X] Read NVFLARE documentation

[X] Began working on "hello world" problem

**Meeting Date/Time:** Week 2 

[X] Found Smart Traffic Management Dataset: https://www.kaggle.com/datasets/smmmmmmmmmmmm/smart-traffic-management-dataset

[X] Implemented lightweight FL model  (3-layer NN) - MAPE ~88%

**Meeting Date/Time:** Week 3

[X] Action Item 1: Implemented benchmark non-FL models for comparison (Linear Regression, Random Forest)

[X] Action Item 2: Added additional layer to NN FL model - MAPE ~85%

[X] Reached out to authors for data citation (no response)

**Meeting Date/Time:** Week 4

[X] Implemented lightweight 2-layer GNN FL model - MAPE ~80%

[X] Utilized standard scaler on numerical data to improve model training

[X] Added lightweight LSTM to benchmark models (24 sequence window)

[X] Added Gradient Boosting benchmark model


**Meeting Date/Time:** Week 5

[X] Researched and calculated proprietary target metric TCI (traffic congestion metric)

[X] Upgraded LSTM, adding bi-directionality and added attention layer

[X] Added rolling and lagging indicators for target variable

[X] Upgraded robustness of GNN FL model - ~<3% MAPE (in-sample)
    - Implemented BatchNorm on feautures
    - Added 4-head Multi-Head Self-Attention
    - Implemented Residual + Feed-Forward "Transformer Block"
    - Added small MLP Regressor
    - Implemented Log Transform on TCI Target Metrics

**Meeting Date/Time:** Week 6

[X] Enabled rigorous out-of-sample testing – added chronological train/val/test split inside the NVFlare partitioner to prevent look-ahead leakage.

[X] Moved log-TCI transform post-split so each subset preserves its own distribution.

[X] Extended the FL runner’s reporting – now logs per-round Train & Val metrics plus first-/last-round Test metrics, enabling live health-checks.

[X] Early results: average Test-MAPE across all sites < 4 %, confirming good generalisation.

**Meeting Date/Time:** Week 7

[X] Exploratory-data-analysis pass #1 – created a full TCI vs. non-TCI visual suite (distributions, heat maps, violin plots).

[X] Contextual plots – weather, humidity, signal-status and accident overlays to build the project narrative.

[X] Correlation heat-map – quantified relationships among core drivers (speed, class counts, temp/humidity).

**Meeting Date/Time:** Week 8

[X] Implemented a FedAvg Bi-LSTM + Self-Attention RNN pipeline (traffic_rnn_fl.py) as a non-graph baseline; re-used the same data loaders, log-TCI target and NVFlare hooks as the GNN for apples-to-apples comparison.

[X] Performance snapshot (round 99, 5 sites): solid improvement over the old single-site LSTM (≈ 25 % MAPE), though still behind the < 4 % GNN.
    - Train-MAPE ≈ 14 % (best site ≈ 11 %)
    - Test-MAPE ≈ 18 % (best site ≈ 15 %) 
    - Discrepency between Train and Test is larger than GNN difference. Suggests weakness on out of sample data. Need to tune for generalizability.

## Other Notes & Information

Current Benchmark Metrics:

![image](https://github.com/user-attachments/assets/16196a43-1f53-4a1b-ad2b-cf48a02e0e60)

Current FL GNN Model Results:

<img width="934" height="598" alt="image" src="https://github.com/user-attachments/assets/69fcf106-8872-43de-8700-dd0cf1026835" />


Current FL RNN Model Results:

<img width="937" height="471" alt="image" src="https://github.com/user-attachments/assets/67f4f745-925d-47b6-8631-618f9c22e082" />

Key EDA Plots:
<img width="1512" height="287" alt="image" src="https://github.com/user-attachments/assets/645eed02-bcdf-441b-9374-a692adc85cfc" />
<img width="1496" height="442" alt="image" src="https://github.com/user-attachments/assets/423f5396-adbd-4523-ae4f-a9a213c8852c" />
<img width="1504" height="404" alt="image" src="https://github.com/user-attachments/assets/1c2ce097-f70f-4763-a061-eef243f5b300" />








# 是否有腦部腫瘤的影像分類

### A. 數據 (Dataset & DataLoader)

#### 1. 資料來源
[https://drive.google.com/uc?id=18RfTvv5NBKuUgMDJjxXb7BLYz31sT_aH]


#### 2. 資料規模
總共251張，no (無腫瘤) 和 yes (有腫瘤)


---

### B. 模型 (Model)

#### 1. 使用深度遷移學習 (Deep Transfer Learning)
使用**ViT-B/16**影像分類模型架構，使用預設參數

***這裡使用 ViT 模型是因為病灶（如腫瘤）可能出現在圖像的任何位置，ViT 的全域視角比傳統 CNN 更有優勢。***


#### 2.凍結部分層（Freeze Layers）
將基礎模型參數凍結，降低小型資料集上的過度擬合風險。

---

### C. 訓練與優化 (Training)

#### 1. 損失函數
`CrossEntropyLoss`

#### 2. 優化器
Adam（預設學習率：`1e-3`）

---

### D. 模型結果與效能評估 (Evaluation)
#### 1. Classification Report

| Class | Precision | Recall | F1-score | Support |
|-------|-----------|--------|----------|---------|
| NO    | 1.000     | 0.857  | 0.923    | 35      |
| YES   | 0.891     | 1.000  | 0.943    | 41      |

**Accuracy:** 0.934 (76 samples)


#### 2.
Sensitivity: 1.0
Precision:   0.8913043478260869
F1 score:    0.9425287356321839

#### 3. confusion_matrix
[[30  5]

 [ 0 41]]
 
 [confusion_matrix](./image/腫瘤混淆矩陣.png)


#### 4.ROC Curve
[ROC Curve](./image/ROC-cruve.png)
#### 5.AUC :0.9679

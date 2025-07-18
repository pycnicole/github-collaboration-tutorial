# 空間統計 Spatial Statistics

ewq6170057-hash
## 空間統計筆記整理

### 課程目標與基本概念
- 空間統計的目的：嘗試用統計方法解釋空間資料的關係（explain spatial data using statistical methods）。
- 地理第一法則（First Law of Geography）：越靠近的事物越相似（"Nearby things are more alike than distant things."）

---

### 空間隨機過程（Spatial Stochastic Process）
- 定義：一組以空間位置為索引的隨機變數
 ```
  {Z(s) | s ∈ D}
 ```
  - s：空間位置
  - D：定義域（空間區域）

- 資料類型：
  - 點資料（Point-referenced）：如溫度、濕度等在特定位置測量的變數 Z(s)
  - 區域資料（Area-referenced）：例如某區域的平均污染濃度 Z(A)

---

### 空間變異與相依性
- 若 Var[Z(A) - Z(B)] 小，表示 A 與 B 在空間上高度相關。
- 通常：
  ```
  Var[Z(A) - Z(B)] < Var[Z(A) - Z(C)]
  ```
  表示 B 較接近 A，比 C 更相關。

---

### 假設檢定範例
- 假設 H0：μ = 20
- 觀測值：Y ~ N(21.5, σ^2)
- 使用 z 統計量：
  ```
  Z = (Y - μ) / σ
  ```
- 若 z = 2.12，p-value = 0.034，拒絕 H0。

---

### 空間資料類型與模型

#### 1. Geostatistics
- 資料為連續空間上某些位置的測量值
- 使用 Gaussian Process 建模

#### 2. Lattice Data
- 資料在固定網格上
- 常用模型：
  - SAR（Spatial Autoregressive Model）
  - CAR（Conditional Autoregressive Model）

#### 3. Spatial Point Pattern
- 資料為事件發生點的位置（如疫病爆發地）
- 常用模型：Poisson Point Process

---

### SAR 與 CAR 模型簡介

- 資料形式：Z = {Z(s1), Z(s2), ..., Z(sn)}

#### SAR 模型：
- 表達方式：
  ```
  Z_i - μ_i = ∑ b_ij (Z_j - μ_j) + ε_i
  ```
- 強調鄰近點的加權平均與誤差項組成觀察值。

#### CAR 模型：
- 假設每個 Z_i 的條件分布依賴於鄰近位置的 Z_j

---

### 小結
- 空間統計結合統計建模與地理資訊的概念
- 各種資料類型需搭配適當模型進行分析
- SAR/CAR 模型為格點資料常見的建模方式
- 地理鄰近性是建模中的核心概念


## 什麼是空間統計？

空間統計（Spatial Statistics）是一門**處理具有空間位置資訊的資料分析方法**，其核心在於：

- **資料具有地理位置資訊（spatial location）**
- **空間相鄰的資料常比遠距資料更相似（第一地理學定律）**
- **考慮資料間的空間依賴性（spatial dependence）**  
- 應用於地球科學、氣象、環境、流行病學、影像處理等多領域。

> 空間統計假設：  
> > 若兩個地點 A 與 B 非常接近，而 C 距離 A 與 B 較遠，則  
> >```Cov[Z(A), Z(B)] > Cov[Z(A), Z(C)]```
> > 
> > 因此：  
> > ```Var[Z(A) - Z(B)] < Var[Z(A) - Z(C)]```

---

## 空間統計的三大類型

### Geostatistics（地質統計）

- 連續空間資料（continuous spatial domain）
- 主要任務：**插值與預測**
- 常見應用：
  - 礦產濃度預測
  - 空氣污染監測設計
  - 大氣與氣候分析
  - 土壤酸鹼值（PH值）測量

### Lattice Data（格點資料）

- 測量位置為**固定格點或不規則格點**
- 適用模型：
  - 同時自迴歸模型（SAR）
  - 條件自迴歸模型（CAR）
  - 馬可夫隨機場（MRF）
- 應用：
  - 疾病地圖製作（如肺癌死亡率）
  - 遙測影像還原與分類

### Spatial Point Pattern（空間點模式）
- 分析資料的出現**位置**與**分佈型態**
- 目標：
  - 偵測是否**隨機、群聚、規則**
  - 量化群聚程度、建模空間點過程
- 應用：
  - 樹木、隕石坑、地震、疾病位置

---

## 空間統計流程（以地質統計為例）

1. 設計取樣計畫  
2. 探索性資料分析（描述統計、繪圖）  
3. 建立空間模型  
4. 估計參數  
5. 空間預測（Kriging等）  
6. 診斷與評估（殘差分析、敏感度分析）  
7. 結果解釋與應用

---

## 常用軟體與 R 套件

| 功能 | 工具 / 套件 |
|------|--------------|
| GIS分析 | ArcMap, GeoDA, Crimestat |
| 空間建模 | R (`sp`, `gstat`, `geoR`, `spBayes`, `fields`, `RandomFields`, ...) |
| 空間點模式分析 | `spatstat`, `splancs`, `spatialkernel`, `aspace` |
| 疾病地圖與格點分析 | `Dcluster`, `spgwr`, `spdep` |
| 生態分析 | `adehabitat`, `vegan`, `pastecs` |
| Bayesian推論 | WinBUGS, `spBayes` |

---

## 空間統計的未來發展

- 時空模型結合（結合時間序列與空間依賴性）
- 高維巨量資料分析（如衛星與感測器資料）
- 更高計算效率與統計精確度的平衡
- 應用於影像復原、分類、醫療監測等新興領域

---

## 推薦參考書

- Cressie, N. (1993). *Statistics for Spatial Data*. Wiley.  
- Schabenberger & Gotway (2005). *Statistical Methods for Spatial Data Analysis*. Chapman & Hall.  
- Diggle, P. (1983). *Statistical Analysis of Spatial Point Patterns*.  
- Ripley, B. D. (1981). *Spatial Statistics*.  
- Geman & Geman (1984). Image modeling with random fields.

What Is Spatial Statistics?
- Data are observed or collected at spatial locations – Spatial data
- Spatial statistics is concerned with analysis of spatial data in which the set of spatial locations are taken into account
- Data and/or locations are modeled as random, and inferences are made about these models or about additional unobserved quantities
- Spatial locations are used in a spatial analysis to model statistical dependence

---

$Y_i \mid Y_{-i} \sim \mathcal{N}\left(\sum_{j \neq i} c_{ij} Y_j, \, \tau^2\right)$

$\mathbf{Y} \sim \mathcal{N}\left(\mathbf{0}, \, (\mathbf{I} - \rho \mathbf{W})^{-1} \tau^2 \right)$

$\mathbf{Y} = \rho \mathbf{W} \mathbf{Y} + \mathbf{X}\boldsymbol{\beta} + \boldsymbol{\epsilon}$

$\boldsymbol{\epsilon} \sim \mathcal{N}(\mathbf{0}, \sigma^2 \mathbf{I})$

$\mathbf{Y} \sim \mathcal{N}\left((\mathbf{I} - \rho \mathbf{W})^{-1} \mathbf{X}\boldsymbol{\beta}, \, \sigma^2 (\mathbf{I} - \rho \mathbf{W})^{-1} (\mathbf{I} - \rho \mathbf{W}^\top)^{-1} \right)$

Spatial correlation decreases with distance, which affects statistical inference. This phenomenon is commonly observed in fields such as forestry, astronomy, epidemiology, and geology.
After merging spatial data blocks, smoothing techniques should be applied to maintain continuity.
Time series regression is used to estimate correlations or model dynamic changes over time.
In regression models, maximum likelihood estimation (MLE) is used to estimate parameters.
In spatial autoregressive (SAR) models, a lower AIC value indicates a better fit.
For conditional autoregressive (CAR) models, the weight matrix w ij is binary (0 or 1) with zeros on the diagonal.
To understand the spatial structure of variables, appropriate weighting and techniques such as the internal difference method can be applied.





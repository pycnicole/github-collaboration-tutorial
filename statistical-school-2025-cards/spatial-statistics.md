# 空間統計 Spatial Statistics
## 什麼是空間統計？

空間統計（Spatial Statistics）是一門**處理具有空間位置資訊的資料分析方法**，其核心在於：

- **資料具有地理位置資訊（spatial location）**
- **空間相鄰的資料常比遠距資料更相似（第一地理學定律）**
- **考慮資料間的空間依賴性（spatial dependence）**  
- 應用於地球科學、氣象、環境、流行病學、影像處理等多領域。

> 空間統計假設：  
> > 若兩個地點 A 與 B 非常接近，而 C 距離 A 與 B 較遠，則  
> > $$ \text{Cov}[Z(A), Z(B)] > \text{Cov}[Z(A), Z(C)] $$
> > 因此：  
> > $$ \text{Var}[Z(A)-Z(B)] < \text{Var}[Z(A)-Z(C)] $$

---

## 空間資料的基本類型

1. **點參考資料（Point-referenced data）**  
   - 每個位置 \( s \in D \subset \mathbb{R}^d \) 有一個隨機變數 \( Z(s) \)
2. **區域參考資料（Area-referenced data）**  
   - 每個區域 \( B_i \) 內的資料為 \( Z(B_i) = \frac{1}{|B_i|} \int_{B_i} Z(s) ds \)

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

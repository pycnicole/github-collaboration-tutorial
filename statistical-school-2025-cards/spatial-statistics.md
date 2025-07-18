# 空間統計 Spatial Statistics
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



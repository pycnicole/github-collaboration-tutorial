# 空間統計 Spatial Statistics
What Is Spatial Statistics?
⚫ Data are observed or collected at spatial locations – Spatial data
⚫ Spatial statistics is concerned with analysis of spatial data in which the set of spatial locations are taken into

account

⚫ Data and/or locations are modeled as random, and inferences are made about these models or about

additional unobserved quantities

⚫ Spatial locations are used in a spatial analysis to model statistical dependence

$Y_i \mid Y_{-i} \sim \mathcal{N}\left(\sum_{j \neq i} c_{ij} Y_j, \, \tau^2\right)$

$\mathbf{Y} \sim \mathcal{N}\left(\mathbf{0}, \, (\mathbf{I} - \rho \mathbf{W})^{-1} \tau^2 \right)$

$\mathbf{Y} = \rho \mathbf{W} \mathbf{Y} + \mathbf{X}\boldsymbol{\beta} + \boldsymbol{\epsilon}$

$\boldsymbol{\epsilon} \sim \mathcal{N}(\mathbf{0}, \sigma^2 \mathbf{I})$

$\mathbf{Y} \sim \mathcal{N}\left((\mathbf{I} - \rho \mathbf{W})^{-1} \mathbf{X}\boldsymbol{\beta}, \, \sigma^2 (\mathbf{I} - \rho \mathbf{W})^{-1} (\mathbf{I} - \rho \mathbf{W}^\top)^{-1} \right)$

## geostastics

做空間預測 找出最適合的分析方法

並非所有資料平均後就會變漂亮

residual用來判斷模型好不好

## lattice data

measurement made at fixed location on a regular or irregular lattice

用途：signal detection

## spatial point pattern

consist of location in a bounded region
123



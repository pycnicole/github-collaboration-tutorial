# 空間統計 Spatial Statistics

<font color="red">**各位修過time series嗎?**</font>

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



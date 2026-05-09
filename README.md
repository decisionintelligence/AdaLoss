# AdaLoss: Adaptive Decomposition Loss for Regular and Irregular Time Series Forecasting

**This code is the official PyTorch implementation of our paper: AdaLoss: Adaptive Decomposition Loss for Regular and Irregular Time Series Forecasting.**

 [![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)  [![PyTorch](https://img.shields.io/badge/PyTorch-2.4.1-blue)](https://pytorch.org/)  

If you find this project helpful, please don't forget to give it a ⭐ Star to show your support. Thank you!

## Introduction

<div align="center">
<img alt="Logo" src="docs/figures/AdaLoss.png" width="100%"/>
</div>


Time series forecasting holds significant value in various domains such as economics, traffic, energy, and AIOps, as accurate predictions facilitate informed decision-making. However, the existing Mean Squared Error (MSE) loss function sometimes fails to accurately capture the seasonality or trend within the forecasting horizon, even when decomposition modules are used in the forward propagation to model the trend and seasonality separately. To address these challenges, we propose an **Ada**ptive and effective decomposition-based **Loss** function called **AdaLoss**. This method uses adaptive exponential moving averages to decompose the time series into seasonal and trend components within the forecasting horizon, and then calculates the loss for each of these components separately, followed by weighting them. As an adaptive loss function, AdaLoss can be seamlessly integrated with any deep learning forecasting model. It is highly effective for both regular and irregular time series forecasting, without requiring manual hyperparameter tuning. Extensive experiments demonstrate that AdaLoss significantly improves the performance of state-of-the-art models across diverse real-world datasets, providing a new perspective on the design of time series loss functions.



## Quickstart
> [!IMPORTANT]
> this project is fully tested under python 3.8, it is recommended that you set the Python version to 3.8.
1. Installation:

> ```shell
> pip install -r requirements-docker.txt
> ```

2. Data preparation:

You can obtained the well pre-processed datasets from [Google Drive](https://drive.google.com/file/d/1vgpOmAygokoUt235piWKUjfwao6KwLv7/view?usp=drive_link). Then place the downloaded data under the folder `./dataset`. 

3. Train and evaluate model:

- To see the model structure of AdaLoss, [click here](https://github.com/qiu69/AdaLoss/blob/main/ts_benchmark/baselines/utils.py).

- We provide the experiment scripts for all benchmarks under the folder `./scripts/multivariate_forecast`. For example you can reproduce a experiment result as the following:

```shell
sh ./scripts/multivariate_forecast/ETTh1_script/DLinear.sh
```



## Results

Long-term multivariate forecasting results. The table reports MSE and MAE for different forecasting horizons F ∈ {96, 192, 336, 720}. The parameters for the baselines are kept consistent with those of [TFB](https://github.com/decisionintelligence/TFB). The better results are highlighted in bold.

<div align="center">
<img alt="Logo" src="docs/figures/exp.png" width="100%"/>
</div>


## Contact

If you have any questions or suggestions, feel free to contact:

- [Xiangfei Qiu](https://qiu69.github.io/) ([xfqiu@stu.ecnu.edu.cn](mailto:xfqiu@stu.ecnu.edu.cn))

Or describe it in Issues.

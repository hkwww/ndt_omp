## Cloud Align Test

本文档记录点云配准的相关测试记录，主要测试平台为：

- **PC**  (Intel® Core™ i5-8600K CPU @ 3.60GHz × 6)
- **RK3588** (4 x Cortex-A76 @ 2.4GHz + 4 x Cortex-A55 @ 1.8GHz)  Base Freq 1.8GHz Turbo Freq 2.4GHz
- **RK3399**  (2 x Cortex-A72 @ 2.0GHz + 4 x Cortex-A53 @ 1.5GHz)  Base Freq 1.5GHz Turbo Freq 2.0GHz



### 测试一 连续帧点云匹配(低速)

- **代码版本：** 未优化 (Commit : 2b8eaa4134a18bba0c9e6c22d4c51b4a66dafe46)

- **测试数据包：**Yang1Lidar (SMSY数据，单激光点云数据与地图点云连续配准)
- **Target点云信息:** 2604920 points
- **Source点云信息:** 16500+ points

**测试结果**

| Platform | Cores | Init (ms) | Max (ms) | Min (ms) | Avg (ms) | EVO-RMSE |
| :------: | :---: | :-------: | :------: | :------: | :------: | :------: |
|    PC    |   2   |  163.122  |  47.618  |  3.212   |  13.424  | 0.015430 |
|  RK3588  |   2   |  344.089  | 129.613  |  5.390   |  28.131  | 0.015435 |
|  RK3399  |   2   |  697.636  | 200.096  |  12.260  |  55.128  | 0.015435 |





### 测试二 连续帧点云匹配(双点云 低速)

- **代码版本：**未优化 (Commit : 2b8eaa4134a18bba0c9e6c22d4c51b4a66dafe46)

- **测试数据包：**Yang2Lidar (SMSY数据，双激光点云数据与地图点云连续配准)
- **Target点云信息:** 2604920 points
- **Source点云信息:** 30800+ points

**测试结果**

| Platform | Cores | Init (ms) | Max (ms) | Min (ms) | Avg (ms) | EVO-RMSE |
| :------: | :---: | :-------: | :------: | :------: | :------: | :------: |
|    PC    |   2   |  167.587  |  67.333  |  7.395   |  25.816  | 0.013055 |
|  RK3588  |   2   |  346.295  | 154.644  |  14.353  |  55.682  | 0.013055 |
|  RK3399  |   2   |  697.821  | 283.357  |  29.076  | 106.315  | 0.013055 |


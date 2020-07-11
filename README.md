# alpha-factor-show
代表性alpha因子测试结果展示
* 数据：日频价量、资金流、订单数据，分钟价量数据；
* 回测划分：样本内为2010-2016，样本外为2017-2020；
* 仅风格（波动率、市值、流动性动量）中性化；
* 在风格中性化的基础上，如果再进行行业中性化，得到的结果没有显著差别；
* 每张图展示因子的四个指标（未考虑任何成本）：tbdf10, top10, top20, IC
  - tbdf10 = top 10% return - bottom 10% return
  - top10 = top 10% return - mean return of all stocks
  - top20 = top 20% return - mean return of all stocks
  - IC = corr($f_t, r_{t+1}$)
* 三种收益率：OCDay2, OCDay5, OCDay10, 分别表示未来2天、5天、10天收益率的平均值，OC表示T+1开盘到T+N收盘；
* 基于日线数据的因子
<p align="center"><img src="https://github.com/Jensenberg/alpha-factor-show/blob/master/B087_net_copy_figures_20100104_20200605.png" width="800"/></p>
  
* 基于分钟数据的因子
<p align="center"><img src="https://github.com/Jensenberg/alpha-factor-show/blob/master/C017_copy_figures_20100104_20200605.png" width="800"/></p>

* 2017-2020指标年平均值

| OCDay2| annret_tbdf10 | sharpe_tbdf10 | maxdd_tbdf10 | annret_top10 | sharpe_top10 | maxdd_top10 | annret_top20 | sharpe_top20 | maxdd_top20 | mean_IC | tstat_IC |
| -------: | ------------: | ------------: | -----------: | -----------: | -----------: | ----------: | -----------: | -----------: | ----------: | ------: | -------: |
|B087_net_copy| 0.24          | 7.59          | -0.01        | 0.12         | 3.66         | -0.01       | 0.12         | 5.38         | -0.01       | 0.02    | 9.38     |
|C017_copy|          0.36 |          10.30 |        -0.01 |         0.16 |         7.44 |       -0.01 |         0.13 |         8.62 |       -0.01 |    0.03 |    11.53 |

* 因子相关系数

<p align="center">
<img src="https://github.com/Jensenberg/alpha-factor-show/blob/master/corr.png"/></p>

* 基于lighGBM的多因子组合
  - 将最终的因子得分进行风险中性化(回归去残差)
  - turnover = $1 - \frac{持有两天的股票数}{每天持有的股票数}$
  - fee = fee(0.15%) * turnover
  - 收益率：OODay1，即T+1开盘到T+2开盘
  - 以全部A股为基准<p align="center"><img src="https://github.com/Jensenberg/alpha-factor-show/blob/master/lgb-reg-cumsum-market-mean.png"/></p>
  - 以中证500为基准<p align="center"><img src="https://github.com/Jensenberg/alpha-factor-show/blob/master/lgb-reg-cumsum-zz500.png"/></p>

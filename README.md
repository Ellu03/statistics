# statistics

## 2026-10-19 · How precise is a sample median? (0.6.0)

```r
library(statistics)
x <- read.csv("bootstrap-median-example.csv")$value
medical_bootstrap_median(x, B = 4000, seed = 20261019)
medical_bootstrap_plot(x, B = 4000, seed = 20261019)
```

In the reproducible simulated sample, median = 7.05, sample IQR = 4.625, and the percentile 95% bootstrap confidence interval is [6.10, 8.20]. IQR describes the spread of observations; the confidence interval describes uncertainty in the estimated median. Resampling assumes independent observations. Small or highly discrete samples can have inaccurate coverage; clustered and weighted samples are unsupported. Teaching example only, not clinical validation.

[Four-platform binaries, simulated data and validation](https://github.com/Ellu03/statistics/releases/tag/v0.6.0)

![Bootstrap median](https://github.com/Ellu03/statistics/releases/download/v0.6.0/bootstrap-median-professional.png)


## 2026-10-16 · Same rate, different precision (0.4.0)

```r
library(statistics)
medical_proportion(c(9, 90, 900), c(10, 100, 1000))
medical_proportion_plot(style="professional")
```

9/10, 90/100 and 900/1000 all give 90%, but their Wilson confidence intervals get narrower. These are individual 95% confidence intervals for independent binomial samples, not Bayesian credible intervals or tests of group differences. Zero observed successes does not establish zero underlying probability. Illustrative counts only; not clinical validation. Clustered, weighted and paired designs are not handled.

[Four-platform binaries, example table and validation](https://github.com/Ellu03/statistics/releases/tag/v0.4.0)

![Proportion precision](https://github.com/Ellu03/statistics/releases/download/v0.4.0/precision-professional.png)


## 2026-10-15 · 基率与阳性预测值（0.3.0）

同一种检验，为什么在低患病率人群中，阳性仍可能多数是假阳性？

```r
library(statistics)
medical_base_rate(c(.01, .05, .20), .90, .95)
medical_base_rate_plot()
medical_base_rate_html("base-rate.html")
```

假设敏感度90%、特异度95%，患病率从1%到5%、20%时，PPV分别为15.4%、48.6%、81.8%。这些是已知假设参数下的数学期望，非真实患者或临床验证。提供独立频数表、两种主题图和可离线调整参数的HTML；无新增依赖。

[0.3.0安装包、离线HTML和教学小数据](https://github.com/Ellu03/statistics/releases/tag/v0.3.0)

四平台R4.5.1检查、原生安装包全新库重装及结果/边界/绘图/HTML导出测试通过。HTML另经Edge桌面1440×1000和390×844窄屏验证，覆盖参数变更、零分母、非法输入和重置。

![基率教学预览](https://github.com/Ellu03/statistics/releases/download/v0.3.0/base-rate-professional.png)


简洁、可复现的统计与医学教学 R 包。公开仓库提供验证后的安装包、预览和精简说明；源码与测试由独立私有构建库保存。

## 医学统计与建模 · 0.2.0

- 基础：描述统计、Welch / 配对 t 检验、组间差异、Holm 两两比较、非参数对照、分类比较。
- 建模：逻辑回归 OR 与 95% 区间，独立模拟验证、AUC、Brier、校准图。
- 诊断：ROC、可调整阈值、敏感度、特异度、PPV / NPV 与 Wilson 区间。
- 生存：Kaplan–Meier、删失标记、在险人数、Cox HR、比例风险诊断。
- 展示：一个离线 HTML 文件，中文标签页、阈值交互、教学数据下载、打印。

```r
library(statistics)
a <- medical_analyze()
medical_html(a, "medical-report.html")
```

只依赖 R 自带基础包及推荐包 `survival`。缺失/非有限值直接报错，避免悄悄删记录。完整数据定义与方法边界见包内帮助和 HTML 的“方法与数据”。

教学要点：**差异分析、区分能力、校准与生存风险回答不同问题；不能用一个 P 值或 AUC 代替全部证据。**

720 条训练记录、360 条独立验证记录均为人工模拟。不是临床工具，不代表真实疗效或外部临床验证。OR 不是风险比；HR 不是绝对风险；Holm 校正不意味着表内所有置信区间都已校正。

从 [Releases](https://github.com/Ellu03/statistics/releases) 下载对应平台安装包。

![医学展示预览](https://github.com/Ellu03/statistics/releases/download/v0.2.0/medical-risk.png)

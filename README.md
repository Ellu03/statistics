# statistics

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

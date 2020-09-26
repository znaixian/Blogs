According to MSCI website as of Sep 2020, "The MSCI factor indexes are rules-based indexes that capture the returns of systematic factors that have historically earned a persistent premium over long periods of time—such as Value, Low Size, Low Volatility, High Yield, Quality and Momentum and Growth. Approximately  USD 236 billion in assets are estimated to be benchmarked to MSCI Factor Indexes"
So I wonder if we have any chance to compete with them under this arena at all.
The very first question I'd ask is if we are able to put together factor strategies? Taking their [MSCI USA LOW SIZE INDEX](https://www.msci.com/eqb/methodology/meth_docs/MSCI_Low_Size_Indexes_Methodology.pdf) as an example. 
At the 4th page, the construction of size index, the key is to compute the weight for each compoenet, instead of simply applying weight sum, they transformed it to log value. Relating to the openquant demo/sample script, where we can use sceening time series, and then quickly breakding down a portfolio per factors, then plot out. It's ideal for such portfolio construction. 
```python 
#factor construction
# Write screening formula with FQL code directly in Open Quant research environment
# Custom Screening Formula
## Define the names of factors that you are interested and enter their corresponding screening formulas

```
Factor Return demonstrated as 
[demo](https://github.com/znaixian/Blogs/blob/master/Contemporary/factor%20return.png?raw=True)



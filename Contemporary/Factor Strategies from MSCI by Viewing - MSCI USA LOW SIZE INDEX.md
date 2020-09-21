According to MSCI website as of Sep 2020, "The MSCI factor indexes are rules-based indexes that capture the returns of systematic factors that have historically earned a persistent premium over long periods of time—such as Value, Low Size, Low Volatility, High Yield, Quality and Momentum and Growth. Approximately  USD 236 billion in assets are estimated to be benchmarked to MSCI Factor Indexes"
So I wonder if we have any chance to compete with them under this arena at all.
The very first question I'd ask is if we are able to put together factor strategies? Taking their [MSCI USA LOW SIZE INDEX](https://www.msci.com/eqb/methodology/meth_docs/MSCI_Low_Size_Indexes_Methodology.pdf) as an example. 
At the 4th page, the construction of size index, the key is to compute the weight for each compoenet, instead of simply applying weight sum, they transformed it to log value. Relating to the openquant demo/sample script, where we can use sceening time series, and then quickly breakding down a portfolio per factors, then plot out. It's ideal for such portfolio construction. 
```python 
#factor construction
# Write screening formula with FQL code directly in Open Quant research environment
# Custom Screening Formula
## Define the names of factors that you are interested and enter their corresponding screening formulas
formulas = {
    'price': 'FF_PRICE_CLOSE_CP(MON,0)',
    'eps': 'FF_EPS(MON,0 L3M)',
    'bps': 'FF_BPS(MON,0 L3M)',
    'roic': "FF_ROIC(ANN_R, 0 L45D)",
    'pe': 'P_PRICE(0) / FF_EPS(MON,0 L45D) * 100',
    'momentum': 'P_TOTAL_RETURNC(-1/0/0,0/0/-1)',
    'ret': 'P_PRICE_RETURNS(1,0,-1/0/0)',
    'bench_ret': 'VALUEX("SP50",P_PRICE_RETURNS(1,0,-1/0/0))',
    'sector': 'GICS_SECTOR()',
    'industry': 'FR_RBICS_NAME_CURR(IND)',
}
#NA analysis using msno package
## Plot the data coverage for each factor
# you can use targets and target_shifts parameters in Screen() to shift factor input forward by a number of period. For example, we can produce one-month, two-month and three-month forward looking returns series from price return
## Create a Screen object with SP500 as investment universe
screen = Screen(universe = univ,
                formulas = list(formulas.values()),
                columns = list(formulas.keys()),
                targets = ['price', 'ret', 'bench_ret'],
                target_shifts = [1,2,3])

#store screen data into a dataframe
df = screen.data
screen
msno.bar(df[[c for c in df.columns if 'fwd' not in c]], 
         color='green', 
         figsize=(8,4))
## Plot the data with "extremely large" pb ratios
columns = ['company_name', 'ticker', 'price', 'bps', 'pb', 'sector', 'industry']
df[columns].sort_values(by='pb', ascending=False).head()

## Quantile the factors
qcuts(df, ['price', 'pe', 'pb'], inplace=True)
qcuts(df, ['roic', 'momentum', 'ret'], ascending=False, inplace=True)

## Plot the 1st quantile and 5th quantile in the same graph
f1 = df[df.pb_q == 1]
fn = df[df.pb_q == 5]
lineplot([f1.pb, fn.pb], labels=['f1 pb', 'fn pb'], figsize=(24, 12), ylabel='Price to Earnings', title='Price to Book for F1 vs FN on PE')

f1 = df[df.momentum_q == 1]
fn = df[df.momentum_q == 5]
lineplot([f1.fwd1_cum_ret, 
          fn.fwd1_cum_ret], 
         labels=['f1 cumulative return', 'fn cumulative return'], 
         figsize=(24, 12), 
         ylabel='Cumulative Return', 
         title='Cumulative Return for F1 vs FN on Momentum')

df.groupby('sector')['eps', 'pb', 'roic'].mean().dropna().plot(kind='bar', 
                                                              stacked=True, 
                                                              colormap=cm.rainbow_r, figsize=(24, 12))
plt.xticks(rotation=45)
plt.title('Mean Analysis by Sector', fontsize=16)
plt.show()         

#correlation heatmap
corr = df.corr()

plt.figure(figsize=(16, 16))
ax = sns.heatmap(
    corr, 
    vmin=-1, vmax=1, center=0,
    cmap=sns.diverging_palette(20, 220, n=200),
    square=True
)
ax.set_xticklabels(
    ax.get_xticklabels(),
    rotation=45,
    horizontalalignment='right'
);
```



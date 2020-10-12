# China Dividend

It always puzzled me that Chinese economy has been booming in the last four decades, GDP has been growing by average of two digits pace. However, you hardly heard that most people have made huge profit in the A share market, on the other hand, anyone jumped in the real estate market in time almost all reaped in great amount of fortune, advancing themselves into solid middle class.
Take a look at the total number and market size of stocks in SHE(shenzhen) and SHG (shanghai) exchanges. 
![number](https://github.com/znaixian/Research/blob/master/pictures/number%20of%20a%20shares.png?raw=true)

![marketsize](https://github.com/znaixian/Research/blob/master/pictures/Total%20market%20cap%20in%20she%20and%20shg.png?raw=true)

We can obtain a quick feel by comparing the major indexes for chines market and American market represented by CSI300 for China and S&P500 for the U.S. in the last 15 years.

The volatility of Chines market is staggering.

The main reason, lot of people argue, and I also agree, is that Chinese stock market is not well developed, it’s fraught with manipulation and fraud. However, as is the universal law, if the economy is healthy and upward, plenty of goods services are produced, the stock market eventually shall represent the status correctly. Just not many people have the tough nerve to endure this kind of volatility.

In addition, China is also going through aging population issue, more and more people are retired, and the new generation are forced to not relying on pension provided by the government, so they are looking for a steady and stable income generator.

A high dividend equity portfolio is certainly a desired option.

First of all, let’s take a look if there any such kind of developed indexes/funds already in the market place.

MSCI has launched “MSCI China A Onshore High Dividend Yield Index” in 2009. The methodology is not obtainable unless inquiry is submitted. According to their marketing pdf, ” The MSCI China A Onshore High Dividend Yield Index is based on the MSCI China A Onshore Index, its parent index, and includes large and mid cap stocks across China securities listed on the Shanghai and Shenzhen exchanges. The index is designed to reflect the performance of equities in the parent index (excluding REITs) with higher dividend income and quality characteristics than average dividend yields that are both sustainable and persistent. The index also applies quality screens and reviews 12-month past performance to omit stocks with potentially deteriorating fundamentals that could force them to cut or reduce dividends.”, testified by their performance as shown below. By the way, the metrics indicates the index’s average dividend yield as of Oct 2019 is 3.65%, the annualized return in last 10 years is 60.9%, in last 5 years is 10%.

![china a onshore dividend](https://github.com/znaixian/Research/blob/master/pictures/msci%20china%20onshore%20dividend.png?raw=true)

Each MSCI High Dividend Yield Index targets companies with high dividend income and quality characteristics and includes companies that have higher than average dividend yields that are both sustainable and persistent. Index construction starts with a dividend screening process: only securities with a track record of consistent dividend payments and with the capacity to sustain dividend payouts into the future are eligible index constituents. Securities are also screened based on certain “quality” factors such as return on equity (ROE), earnings variability, debt to equity (D/E), and on recent 12-month price performance. The goal is to exclude stocks with potentially deteriorating fundamentals that could be forced to cut or reduce dividends. From the list of eligible companies, only those with higher than average dividend yields are selected for inclusion in the index. Issuer weights are capped at 5%. The index is market cap weighted and rebalanced semi-annually in May and November.” There are 85 holdings as of present (Nov2019) and the dividend yield on average is about 4%.

Another fund – Matthews Asia Dividend Fund, according to it’s disclaimer on their website, “Under normal market conditions, the Matthews Asia Dividend Fund seeks to achieve its investment objective by investing at least 80% of its net assets, which include borrowings for investment purposes, in dividend-paying equity securities of companies located in Asia. The Fund may also invest in convertible debt and equity securities. The Fund seeks to provide a level of current income that is higher than the yield generally available in Asian equity markets over the long term. ” So this is quite an actively managed mutual fund, not comparable to such thematic index funds.

In my experimental work, with the following simple steps:

A shares 3-month average Market cap and 6-month average ADTV ranked to obtain quintiles, exclude both bottom quintiles (second bottom quintile for both metrics)
Query dividend for the last 4 years, the current year dividend must not equal to 0, and each year, it’s greater or equal than last year’s dividend (this is deleted, only keeps the metric to ensure there is non-zero dividend issued)
Calculate free cash flow yield and dividend yield, rank them to obtain a percentage score, calculate compscore = 50%*dividend yield rank + 50% cash flow rank (actually I use mean of the two rank here, so if one value is missing, the stock won’t be lopsided penalized by losing entirely 50%)
Rank all by compscore, choose top 30. Equal weighted, and backtested ;

Also use top 30 portfolio, do dividend based weighting, and backtested.

![my dividend portfolio](https://github.com/znaixian/Research/blob/master/pictures/china-dividend-top-30-ew-9-years.png?raw=true)

Compared to the rival product MSCI High Dividend Yield Index returns only about 6% in a 10-year time frame, this prototype is better.

So what are these high dividend companies, let’s cut two screenshot, one in 20110603,
![2016](../Research/pictures/top%20list%202016.png)
The landscape changes a lot. Over the years, the dividend yield on average has been stepping up steadily too.
![2020](../Research/pictures/2019%20top.png)
And if we take the lens of RBICS industry Economy level, it further reveals that Finance has always been the major sector, and in recent years, it’s been more dominant or concentrated by Finance.

The landscape changes a lot. Over the years, the dividend yield on average has been stepping up steadily too.
![dividend yield](../Research/pictures/Screenshot%202020-10-11%20161507.png)

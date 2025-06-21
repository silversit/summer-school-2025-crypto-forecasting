# CASE: THE A.I. CRYPTO TRADER

Authors: Angel Marchev, Jr., Alexander Efremov, Petar Nikolov, Pavel
Nikolov, Boryana Pelova

## 1. INTRODUCTION

In attempt to make a case which is to be somewhat universally understandable by various types of students, the case is financial time-series prediction, while making it more engaging with the hot topic of cryptocurrencies. The case integrates knowledge from various sources -- Crypto Currencies, Quantitative Finance and Machine learning. At the same time the case is stratified as the teams solving it could complete various levels -- as far as they could solve it.  

## 2. BUSINESS PROBLEM FORMULATION

The goal is to build a successful investing/trading model on the cryptocurrency markets. The data consists of time-series of various cryptocurrencies (in 1-minute steps) prices and 24 hour volumes. The data could also be enriched by the team.

Cryptocurrencies' portals: [Link 1...](https://www.ccn.com/) ; [Link 2...](https://www.coindesk.com/) ; [Link 3...](https://coinradar.io/) ; [Link 4...](https://coinmarketcal.com/)

Crypto guides & glossaries: [Link 1...](https://cryptominded.com/glossary-cryptocurrency-terms-need-know/) ; [Link 2...](https://buybitcoinx.com/glossary/) ; [Link 3...](https://blokt.com/cryptocurrency/terminology) ; [Link 4...](https://mycrypto.guide/)  

Cryptocurrencies data: [Link 1...](https://coinmarketcap.com/) ; [Link 2...](https://www.blockchain.com/) ; [Link 3...](https://www.cryptocompare.com/) ; [Link 4...](https://bitcoinwisdom.com/) ; [Link 5...](https://coinlib.io/)  

The case has two levels of difficulty -- in order to go to start solving the next level, you would need to complete the previous:

-   **LEVEL 1:** Make a prediction model of the major cryptocurrencies' prices

The process of investment could be analyzed in several consecutive phases, which are processes of transforming information. First are the input processes -- from the environment, from the current state of the investment and from the investors' goals. Using these inputs, the next phase is a predictor for forecasting/estimating the expected values for the significant variables and the external factors. Statistical analysis of past portfolio structure is also necessary. The prediction model should be able to forecast the prices of the major cryptocurrencies throughout the most volatile periods with some acceptable accuracy, utilizing all available information (including additional enrichment of data) for one period ahead.

-   **LEVEL 2:** Make an autonomous A.I. decision-maker for trading/investing.  

Autonomous investment is a concept which implies that the process of investment management should be conducted by and self-maintained by non-human entity. The autonomous investment corresponds to the ever-faster changing investment environment accelerated by the rapid development of the communicational and computational abilities of the modern computer. So as an effort to keep up with the technological advancements in the area as well as trying to keep the playing field level, there is now a new tendency among researchers to propose autonomous solutions for trading (while of course making it harder and harder for human entities to participate). The general approach preached by the authors of the current case is based on the idea of machine learning. The A.I system should be able to make use of the available data (including the predictions from level 1) to form and simulate a viable investment strategy, working on its own for the whole period of supplied data.

## 3. RESEARCH PROBLEM SPECIFICATION

This section consists of problem description from data science point of view. It is meant to assist the teams to what general directions should
they take in their solution.  

**Тhe concept of the case**

Generally the case requires series of historical simulation experiments over the crypto currencies market, using the supplied pricing data. Every experiment uses prehistory ex-post data to predict ex-ante several points into the future. These predictions are then compared with the real data for these same several points and this concludes one experiment. To begin the next experiment the historical ex-post data window slides to the future and starts over again. All of the "models of investors" are to be back-tested on the unified competition data track. Such competition track consists of complete time series of all possible assets. The back-testing is done for every data-point (historical trading time moment) with all possibilities (all assets available for trading in that time moment). The direct result of such systematic approach would be a ranking list of the most successful (according to given criteria) A. I. Investors.

![](/img/image1.png)

Every A. I. investor is to be tested on each data point with the full variety of possible modifications. There is a minimal incremental step of one observation. The historical data window, which is used for estimation, reflects the period of previous data that the model uses. With each advance to the next data point, the window "slides" forward as well. The horizon of prediction (minimum one observation) also slides forward. For sake of equivalency among the teams we will assume that the earliest period for prediction (level 1) or investment decision (level 2) would be the first time data point after the start of the dataset.

The prediction/investment horizon would be 1 time step ahead, but it is possible to implement methods working for more steps ahead. The sliding step of the prediction window would be 1 time step, but again the teams may implement systems which re-evaluate at longer time periods. The last
simulation experiment should finish with the last data point of the supplied data. During the historical simulation all necessary computations are calculated according to the business logic or the algorithms of the experimented model of investor based on the all the data points in the data set. As a result, there is a new formed data array with selected solutions for each observation. So that this new data array has dimensions of k columns and m-1-D rows, where k is the number of all assets (some/most/all of them could be equal to 0), included in the data set, m is the number of all observations, and D is the size of the necessary pre-history data for the given model of investor. The A. I. investor reconsiders his investment portfolio every L periods, where L is the investment horizon.

**General Assumptions for the case**

These assumptions are necessary for the methodically correct run of the historical simulation:

-   the investor is independent, private, small entity investing own  funds;

-   the transactions (frequency and amounts) do not influence the market  prices;

-   all other investment markets except for the presented in the data  set are disallowed;

-   minimum discretisation step is 1 minutes;

-   the moment "Now" is notated by t=0 or t(0)

-   all necessary predictions are based on ex-post data before t(0);

-   technical limitations -- the once trained models should be able to  work on regular computer

**Level 1**

The main aim of time series modeling is to carefully collect and rigorously study the past observations of a time series to develop an appropriate model which describes the inherent structure of the series. This model is then used to generate future values for the series, i.e. to make forecasts. Time series forecasting thus can be termed as the act of predicting the future by understanding the past. There are many techniques which could be used to forecast the cryptocurrencies' prices, and the choice would be left to the discretion of the participants. Some
of the main classes of forecasting models are: Regression analysis; Autoregression & moving averages; Support vector machines, Artificial
neural networks, etc.

Introduction to Time series forecasting: [Link 1...](http://www.forecastingprinciples.com/) ; [Link 2...](https://www.altexsoft.com/blog/business/time-series-analysis-and-forecasting-novel-business-perspectives/) ; [Link 3...](http://www.saedsayad.com/docs/Time%20Series%20and%20Forecasting.pdf) ; [Link 4...](https://arxiv.org/ftp/arxiv/papers/1302/1302.6613.pdf)

Examples of Time series forecasting: [Link 1...](https://www.analyticsvidhya.com/blog/2016/02/time-series-forecasting-codes-python/) ; [Link 2...](https://www.analyticsvidhya.com/blog/2018/02/time-series-forecasting-methods/) ; [Link 3...](https://towardsdatascience.com/using-lstms-to-forecast-time-series-4ab688386b1f) ; [Link 4...](https://tensorflow.rstudio.com/blog/time-series-forecasting-with-recurrent-neural-networks.html)

[Have a look at an article, written especially for this case...](https://www.datasciencesociety.net/tech-stack-suggestions-cryptocurrency-challenge/)

**Prediction scoring**

The prediction models should be tested on the prices of the chosen 55 cryptocurrencies (see below) and every metric would be averaged among
all currencies in the final score. For the sake of scoring the accuracy of the prediction models, several various random periods will be chosen
for testing out of the supplied data, with each testing period consisting of 24 hours. These periods would be unknown to the participants and would be chosen specifically for their contradictory movements and volatility. The prediction models should be able to perform within certain limits and will be competed among each other on the following metrics:

1\. The **mean absolute percentage error** (**MAPE**) is a measure of prediction accuracy of a forecasting. It is measuring how close the
prediction is to the actual data for the whole period. It expresses accuracy as a percentage, with the smallest possible value being most
desirable:

![](/img/image2.png)

Where:

yt -- actual data point at period t

ft -- forecasted data point for period t

n -- total number of periods considered for evaluation

2\. The **directional symmetry** **(DS)** statistic gives the percentage of occurrences in which the sign of the change in value from one time period to the next is the same for both the actual and predicted time series. The DS statistic is a measure of the performance of a model in predicting the direction of value changes. The case DS = 100 % would indicate that a model perfectly predicts the direction of change of a time series from one time period to the next. The desirable score here should be higher than 50%.

![](/img/image3.png)

Where:

yt -- actual data point at period t

ft -- forecasted data point for period t

n -- total number of periods considered for evaluation

3\. As an additional and necessary characteristic of the prediction model will be calculated stability over the testing sets of periods. The stability will be measured by **coefficient of variation of the mean absolute percentage error. **Coefficient of variation is a relative measure of dispersion that corresponds to standard deviation, but it is expressed in percentage terms, which means it could be compared across different prediction models. The coefficient would be computed among the values of MAPE for the various testing sets of periods. The desired value should be less than 1.

![](/img/image4.png)

Where:

Mi -- mean average absolute error for testing set i

R -- generalized coefficient of variation

m -- total number of testing sets

4\. In order for the prediction models to have any practical value **Computational efficiency** will be computed as a relative time to calculate the next prediction compared to the minimal time step of the next actual observation. The model should be able to be executed on a regular computer (1 cpu 2 GhZ, 4 GB RAM will be assumed) but there are no restrictions for the computer on which the model is trained. Desired value is minimum possible.

![](/img/image5.png)

Where:

Tc -- time for calculating prediction for currency c in seconds

p -- total number of predicted currencies

Tg -- time interval for next actual data point in seconds

U -- relative time for execution of all predictions in % of time interval

5\. The combined score for each model will be computed as a linear combination of the above specified metrics averaged over the studied crypto currencies. To mitigate the possibilities for cheating the competition scoring may be done at a dedicated server. Also the the finalists' models may be trained at a dedicated server. Note that this score is one single number for the whole team solution. The highest possible value of the score is most desirable. Please, have in mind that this score may be a negative number.

![](/img/image6.png)

Where: Z -- combined score D -- mean directional symmetry over the different testing periods M -- mean MAPE over the different testing periods R -- generalized coefficient of variation U -- relative time for execution of all predictions in % of time interval  

**Level 2**

Over the years a significant number of portfolio models, methods, procedures and strategies ("investors") have been proposed by theoreticians and practitioners in the field. Application of each of them should be considered as a systematic process consisting of several phases (i.e. goal setting, data collection, data structuring, statistical testing, enforcing limitations, forecasting, generating and developing feasible solutions, selection of optimal solution, realizing the investment solution, retrieving feedback of the significant outcomes, etc).

You should build an autonomous trading/investment system which presents the best chance for profiting on the cryptocurrencies market. This system (A.I.) should run throughout the whole period of the data set, starting on the first time data point and finishing on the last time step. The A.I should be able to decide trades when to buy and sell the cryptocurrencies on its own without human interaction. And the task at hand is to simulate what would be the results of such A.I. for the whole data set period. The participants have the choice to which approach to use to build their autonomous trading system. Possible (out of many) approaches are Trading robots (typically directed towards trading with one or two assets), Statistical arbitrage (utilizing pricing inefficiencies among several assets), Autonomous portfolio management (using dynamic optimization techniques to allocate capital among many assets).

Trading robots introduction: [Link 1...](https://www.investopedia.com/terms/forex/f/forex-trading-robot.asp) ; [Link 2...](https://www.forexfraud.com/forex-articles/forex-automatic-trading-robots.html) ; [Link 3...](https://www.investopedia.com/articles/active-trading/081315/how-code-your-own-algo-trading-robot.asp)

Trading robot example: [Link 1...](https://code.tutsplus.com/tutorials/create-a-algorithm-trading-robot-the-basics-of-writing-a-expert-advisor-in-mql4--cms-27984)

Trading robot builders: [Link 1...](http://www.forexeadvisor.com/expert_generator.aspx) ; [Link 2...](https://fxeabuilder.com/ea-builder/)

Statistical arbitrage introduction: [Link 1...](https://www.investopedia.com/terms/a/arbitrage.asp) ; [Link 2...](https://www.investopedia.com/ask/answers/04/041504.asp) ; [Link 3...](https://en.wikipedia.org/wiki/Statistical_arbitrage) ; [Link 4...](https://www.quantinsti.com/blog/statistical-arbitrage/)

Statistical arbitrage examples: [Link 1...](https://www.nasdaq.com/article/dont-be-fooled-by-the-fancy-name-statistical-arbitrage-is-a-simple-way-to-profit-cm254669) ; [Link 2...](http://jonathankinlay.com/2015/03/successful-statistical-arbitrage/)

Statistical arbitrage advanced examples: [Link 1...](https://arxiv.org/ftp/arxiv/papers/1405/1405.2384.pdf) ; [Link 2...](https://www.math.nyu.edu/faculty/avellane/AvellanedaLeeStatArb071108.pdf)

Investment portfolio introduction: [Link 1...](https://www.investopedia.com/terms/p/portfoliomanagement.asp) ; [Link 2...](https://www.investopedia.com/terms/p/passivemanagement.asp) ; [Link 3...](https://www.investopedia.com/terms/d/dynamic-asset-allocation.asp)

Investment portfolio further reads: [Link 1...](https://en.wikipedia.org/wiki/Modern_portfolio_theory) ; [Link 2...](https://www.thebalance.com/successful-investing-portfolio-management-357853) ; [Link 3...](http://pages.stern.nyu.edu/~adamodar/New_Home_Page/background/portmgmt.htm)

Investment portfolio advanced example: [Link 1...](http://sci-hub.tw/10.1063/1.4902492)

**Additional assumptions for level 2**

In order to define the case for Level 2, additional assumptions about the trading procedures are needed. Assumptions on simulating the investment value:

-   the initial invested amount is 10000 USDT, simulating a small  investor;

-   being small investor also means, that the transactions do not  influence the market prices;

-   there is no new capital inflow, nor capital outflow (no new funds  added, no funds withdrawn) for the full period of the data;

-   the initial capital could be invested no earlier than the first time  data point ;

-   if the investment value reaches 0 USD (or real return of -100%), the  investor is insolvent/ bankrupt (none-the-less you should keep the  results even from these tryouts as they are usually useful  experiments);

![](/img/image7.png)

Where:

Mv (t) -- market value of investment at the moment t

Nui (t) -- equivalent number of units of asset i at moment t

Pi (t) -- market price of asset i at moment t

k -- total number of assets

-   the value of the USDT positions is unchanging (regardless of the  real world trade possibilities for USDT), which means zero return  -- the case is about cryptocurrencies, not FIAT currencies;

-   If the investor runs into non-computable values by the A.I.'s  procedures (the model could not present a realizable result and  there is not possible solution for the current time moment), the  states of investments in all assets are kept as the values from  previous time moment;

-   No fundamental events influence the value of the investment (e.g. do  not account for effects from forks, airdrops, burns, etc.).

Assumptions on simulation the market:

-   there is perfect liquidity on the market, so the investor could  always make a trade at the given price;

-   all transactions in time moment t (and after moment t-1) are made at  price P(t);

-   there is no short selling;

-   there is no margin trading.

Assumptions on simulation the market frictions:

-   all trades are charged 0.25% of the turnover of the trade;

![](/img/image8.png)

Where:

Nui (t) -- equivalent number of units of asset i at moment t

Pi (t) -- purchase price of asset i at moment t in USDT

Bf -- exchange fee (0.0025)

-   the trading fee includes all blockchain transaction fees (since  there are no withdrawals allowed);

-   no income taxes are owed to any fiscal entity;

-   no market spread -- all trades are simulated on the given market  prices;

-   The minimum trade value for orders within same time frame and with  the same cryptocurrency is 0.001 BTC (100,000 Satoshis);

-   The maximum trade value for orders within same time frame and with  the same cryptocurrency is 0.5 BTC;

-   Rationalizing the transactions -- due to the various market  frictions it is rational that before realizing a transaction the  new desired investment structure (computed at period t) is  compared to the old investment structure (computed at period t-1),  so that the new market order trades only the differences.

![](/img/image9.png)

Where:

MOri(t) -- market order in number of units of asset i at moment t

Nui (t) -- equivalent number of units of asset i at moment t

-   for any other market frictions you should refer to the rules of  Bittrex  ([here...](https://support.bittrex.com/hc/en-us/sections/200692094-Trading))

**Investment scoring**

1.  **Risk-adjusted return measure. **In order measure performance of  the investment A.I. it is essential to implement a viable  indicator. It has to be risk adjusted return due to:

-   Firstly -- since all possible benefits from investing in a given  asset are already reflected in the individual return of the asset,  then the return becomes general measure of the benefit.

-   Secondly -- the return alone is not a good measure as the same value  of return may be achieved at various values of risk. Ergo risk  adjusted return is a better measurement for risky investments.

-   Thirdly -- using risk adjusted return effectively compresses  two-dimensional problem into one-dimensional and among other  advantages it also relaxes the multi-criteria optimization problem  to single-criterion optimization problem.

The risk adjusted return should be computed by using an asymmetric measure modified from Sortino ratio (Frank A. Sortino and Robert van der Meer. "Downside Risk." Journal of Portfolio Management. Vol. 17, No. 5, Spring 1991, pp. 27--31). The asymmetric measures calculate the risk far more precisely, but require at least twice as many data points for computing a robust estimation. Desired value is maximum possible.

![](/img/image10.png)

Where:

G -- Generalised asymmetric risk adjusted return measure

Rp -- Return of the investment A.I. for the whole data set

Rp(t) -- Compound return of the investment A.I. for time data point t

Mv(M) -- Market value of the investment at data point M (endpoint)

MV(1) -- Market value at the start of the competition (10000 USD)

ν0(Rp) -- Lower partial moment of return with minimum acceptable return = 0

2\. In order for the A.I. investor to have any practical value **Computational efficiency** will be computed as a relative time to calculate the next solution compared to the minimal time step of the next actual observation. The A.I. should be able to be executed on a regular computer but there are no restrictions for the computer on which the model is trained. Critical value is \< 1, (in other words time for calculation should be less than 300 seconds).  

![](/img/image11.png)

Where:

Ts (t) -- time for calculating solution t in seconds

Tg (t) -- time interval for actual data point t in seconds

U (t) -- relative time for execution of solution t in % of time interval

## 4. DATA DESCRIPTION   
The used dataset is the same for all participants but could be enriched with any publicly available data (of course any enrichment should be diligently described). The dataset is considered a test track for tryout, evaluation, competition and comparative analysis of the A.I. investors.

[You could download the dataset here...](/data/)

**Data transcript**

Description of each variable. The data structure of all files (\*\_USDT_1m.csv), which contain the OHLC prices in USDT, and trading volumes. There are files for every cryptocurrency (known by the begining code of the filename).


|  name                      | max_length |  notes
|----------------------------|-----------|-------------------------------
| timestamp                  | 19        | time stamp for record
| open                       | 10        | open price for the period (USDT)
| high                       | 10        | highest price for the period  (USDT)
| low                        | 10        | lowest price for the period (USDT)
| close                      | 10        | open price for the period (USDT)
| volume                     | 9         | Traded volume for the period (USDT)


**Possible data challenges and solutions** 

-   Data challenge: there are price time series which do not have enough data points to conduct reasonable analysis or to apply a certain     method.

    -   Solution: making a well-grounded selection of the assets in the research database, but still leaving as many assets as possible         in the data set.

-   Data challenge: in the initial trading sessions of some assets there are relatively large periods of trading inactivity or strange,     uncharacteristic behavior.

    -   Solution: eliminating the boundary effects by removing certain number of initial observations.

-   Data challenge: in price time series there is missing data.

    -   Solution: data imputation in the time series. There are many approaches to data imputation of financial time series.         According to Lazarov, D., "Missing data evaluation in financial time series", these are the most promising ones:

        -   LVCF -- Last value carried forward imputation  
        -   LINT -- Linear interpolation  
        -   R1 -- Multivariate regression imputation  
        -   NP100 -- Non-parametric multivariate regression imputation using a moving window of length 100  
        -   MARX1 -- Multivariate autoregression imputation of lag 1  
        -   AR5X -- Univariate autoregression imputation of lag1 -- lag5  
        -   MLP -- Univariate multi-layer perceptron imputation

-   Data challenge: not enough data for a given A.I. trader.

    -   Solution: collect additional data and enrich the data set. This may include economic/business data, data from various markets, etc. Some popular data sources for cryptocurrencies are following (but any data source is acceptable, as long as it is publicly accessible):

        -    [Link1...](https://coinmarketcap.com/), [Link2...](https://www.coinapi.io/), [Link3...](https://www.cryptodatasets.com/), [Link4...](https://www.cryptocurrencychart.com/), [Link5...](https://www.kaggle.com/jessevent/all-crypto-currencies/data), [Link6...](https://www.investing.com/crypto/), [Link7...](https://coinmetrics.io/data-downloads/)

The following metrics should be calculated, written in the article and uploaded:

-   M (MAPE) for every currency for every test period:

-   D (Directional Symmetry) for every currency for every test period

-   R (coefficient of variation of MAPE) for every currency

-   U (computational efficiency) one number for the whole solution

-   Z (prediction score) one number for the whole solution


-   Level 2:

You should upload one matrix containing the relative weights of the investment back simulation in csv file, named portfolio_sim.csv. The matrix should contain the same number of lines as the data files + 1 header row) and 56 columns -- one for each crypto-currency and 1 column for USDT position. Every cell in the matrix consists of a value between 0 and 1 and it means what share of the total capital you have invested in this currency (column) at this time point (row). Every data row sums up to 1.00 (or 100%) which is guaranteed by the USDT position. If your trader AI doen't want to invest in any crypto currencies, it may choose to put 100% of the capital in USDT (do not forget that by rule USDT doesn't bring any return).

The following metrics should be calculated, written in the article and uploaded: G Generalised asymmetric risk adjusted return measure for the
whole data set U (computational efficiency) for each time point (it should be \< 60 seconds)

**Questions:**

1.  Level 1: Prediction modeling

What necessary data preparation did you need? Which is the most suitable method for forecasting cryptocurrencies? Which cryptocurrencies were
hardest to predict? What anomalies in behavior of the cryptocurrencies did you detect?

1.  Level 2: A.I. Trading

How many assets did you include in your A.I. Trading? How did you make the selection? Which is the best Risk adjusted return have you achieved?
Which model? Would this be the winning model if we ranked them on Return only? What is the optimal time for reevaluating the investment (optimal
investment horizon)? What is the optimal size of the training data set? (Bonus) If you use the calendar for fundamental events such as airdrops,
burns, forks ([here...](https://coinmarketcal.com/pastevents?form%5Bdate_range%5D=25/01/2018 - 14/04/2018&form%5Bcategories%5D%5B0%5D=0&form%5Bcategories%5D%5B1%5D=3&form%5Bcategories%5D%5B2%5D=7&form%5Bsort_by%5D=&form%5Bfilter_by%5D=&form%5Bsubmit%5D=&page=5)), how would you change your A.I. Trader to be more profitable?

## 5. READER ON FINANCE TERMS

1.  **Glossary**

Investment

-   The investment process is a chain of considerations and actions for  an individual, from thinking about investing to placing buy/sell  orders for investment assets. (Investments, Bodie, Kane, Marcus,  pp. 858)

-   The sacrifice of certain present value for (possibly uncertain)  future value. (Investments, Sharpe, Alexander, Bailey, pp. 1013)

-   Investing is a process of consciously sacrificing own resources in  the pursuit of future reward or goal. Important notion is that necertainty of future events may clash with some current actions.  None of the future outcomes is guaranteed to offset the undertaken restriction of investor's degrees of freedom (Alexander et al,  1993, pp. 840).  

-   Although generally it is accepted that "investing" differs from  "trading", based on the term of the strategy (longer terms for  investing), for the current needs trading will be assumed as a  special case of investing, as it fits perfectly well with the  above definitions (presuming "future" to be both short and long  term).

Investor

-   The investor is an entity (physical or legal), purposefully using  financial (and other) resources for investment and pursuing future  rewards. It is assumed that such entity acts rationally as a real  Homo Economicus (Mill, 1836).

Investment asset/asset

-   asset is an instrument that can be traded freely and easily on a  well-developed market. (Investment Science, Luenberger, pp. 40)

-   asset (a.k.a. investment instrument, investment asset, position)  according to Marchev (2012) is investment opportunity, traded  freely on a transparent market which transmits publicly enough  relevant information.

Organized market

-   A central location where trading of assets is done under a set of  rules and regulations.

-   A mechanism designed to facilitate the exchange of financial assets  by bringing buyers and sellers of assets together. (Investments,  Sharpe, Alexander, Bailey, pp. 1010 -1017)

-   Organized exchange are centralized auction-type markets, while the  over-the-counter market is an intricate network of asset dealers  that take position in various assets and boy and sell from their  own portfolios.(Modern Investment Theory, Haugen, pp. 26)

Market price

-   A market price is the last price at which an asset traded, meaning  the most recent price on which a buyer and seller have agreed and  at which some amount of the asset was transacted.

-   Closing price is the final price at which an asset was traded for a  given trading period. The closing price represents the most  current valuation of an asset until the end of the next trading  period. Note that the trading period could be virtual (for the  sake of research) and not officially regulated.

Return

-   A rate of return expresses the percentage change in your wealth from  one period to another. (Modern Investment Theory, Haugеn, pp. 389)

-   Returns from investing are crucial to investors; An assessment of  return is the only rational way (after allowing for risk) for  investors to compare alternative investments that differ in what  they promise. The measurement of actual (historical) returns is  necessary for investors to assess how well they have done or how  well investment managers have done on their behalf. (Investments  Analysis and Management , Jones, pp. 114)

Risk

-   Risk means uncertainty about future rates of return. (Investments,  Bodie, Kane, Marcus, pp. 123)

-   The chance that the actual outcome from an investment will differ  from the expected outcome. (Investments Analysis and Management ,  Jones, pp. 11)

-   A measure of uncertainty about the outcome from a given event. The  greater the variability of possible outcomes, on both the high  side and the low side, the greater the risk. (Foundations of  Financial Management, Block, Hirt)

-   Risk is identified with the dispersion of returns, i.e. with  possible deviations (both positive and negative) from the expected  return. (Capital investment & financial decisions, Levy, Sarnat,  pp. 237)

-   The standard deviation around the expected return. (asset Analysis  and Portfolio Management, Fischer, pp. 560)

Liquidity

-   Liquidity is the ease (speed) at which an asset can be sold and  still fetch a fair price. (Investments, Bodie, Kane, Marcus, pp.  864)

-   Liquidity refers to the ease of converting an asset into money  quickly, conveniently, and at little exchange cost. (asset  Analysis and Portfolio Management, Fischer, pp. 6)

-   The ability to sell an asset quickly without having to make a  substantial price concession. (Investments, Sharpe, Alexander,  Bailey, pp. 1014)

Arbitrage

-   Arbitrage is the simultaneous purchase and sale of an asset to  profit from a difference in the price. It is a trade that profits  by exploiting the price differences of identical or similar  financial instruments on different markets or in different forms.  Arbitrage exists as a result of market inefficiencies and would  therefore not exist if all markets were perfectly efficient.

-   Statistical arbitrage comprises a set of quantitatively driven  trading strategies, looking to exploit the relative price  movements across thousands of financial instruments by analyzing  the price patterns and the price differences between financial  instruments.

-   Possible scenarios for exploiting arbitrage conditions:

    -   Market Neutral Arbitrage -- involves taking a long position in an undervalued asset and shorting an overvalued asset simultaneously. The assets should be selected to have similar volatilities and thus, an increase in the market will cause the long position to appreciate in value and the short position to depreciate by a roughly the same amount.

    -   Cross Market Arbitrage -- exploiting the price discrepancy of the same asset across markets, buying the asset in the lower-valuing market and selling it in the highly valuing market simultaneously.

    -   Cross Asset Arbitrage -- using the price discrepancy between a financial derivative and its underlying asset.

Investment portfolio

-   Collection of assets. (Investments, Sharpe, Alexander, Bailey, pp.  167)

-   The assets held by an investor taken as a group. (Investments  Analysis and Management , Jones, pp. 7)

-   assets that have return and risk characteristics of their own, in  combination, make up a portfolio. (asset Analysis and Portfolio  Management, Fischer, pp. 2)

-   Portfolio management is the process of combining assets in to a  portfolio tailored to the investor's preferences and needs,  monitoring that portfolio , and evaluating its performance.  (pp. 2) Portfolio theory deals with the big picture -- the risk  and return attributes of the investor's overall portfolio of  assets. (pp. 810) (Investments, Bodie, Kane, Marcus)

-   The purpose of using a portfolio approach is to improve the  conditions of the investment process by obtaining such properties  (values of significant variables) of the combined assets that are  not obtainable by any single asset. The most often (but not the  only) considered significant variables are risk and return. A  certain configuration of risk and return is only possible within a  given combination of assets. Improving risk and return conditions  through portfolio management is diversification (Marchev, 2012a).

Diversification

-   Another means to control portfolio risk is diversification, by which  we mean that investments are made in a wide variety of assets so  that the exposure to the risk of any particular asset is limited.  (Investments, Bodie, Kane, Marcus, pp. 810)

-   The process of adding assets to a portfolio in order to reduce the  portfolio's unique risk and, thereby,the portfolio's total risk.  (Investments, Sharpe, Alexander, Bailey, pp. 1007)

-   The variance of the return of a portfolio can be reduced by  including additional assets in the portfolio, a process referred  to as diversification. (Investment Science, Luenberger, pp. 151)

-   Diversification is related to the Central Limit Theorem, which  states that the sum of identical and independent random variables  with bounded variance is asymptotically Gaussian (the notion of  diversification can be extended to more general random variables  by the concept of mixing). (Robust Portfolio Optimization and  Management, Fabozzi, pp. 19)

-   The more traditional forms of diversification have concentrated upon  holding a number of asset types (stock, bonds) across industry  lines (utility, mining manufacturing groups). (asset Analysis and  Portfolio Management, Fischer, pp. 560)

-   An investor can construct a diversified portfolio and eliminate part  of the total risk, the diversifiable or non-market part  (unsystematic part). (Investments Analysis and Management , Jones,  pp. 254)

**Computation considerations on portfolio significant
variables** The **mathematical description of a portfolio** is in the form of vector consisting of k+1 positions each with respective weights, where k is the total number of assets and the additional position is the cash position c(t). For unwanted positions the values are set to 0. Not invested funds are always assumed to be in the cash position. The sum of all weights is equal to 1.00. In brief the mathematical description of an investment portfolio is a k+1-dimensional vector of weights summing to 1.00 (i.e. a singular simplex).

![](/img/image12.png)

where:

W(t)- weight structure of the portfolio at discrete time (t)

c(t) -- relative weight of the cash position at discrete time (t)

wi(t)- relative weight of i-th asset at discrete time (t), subject to
(no short positions):

![](/img/image13.png)

To calculate **return of each asset **at the discrete time t the
particular case is considered, where:

-   Short selling is not possible transaction, meaning that the discrete  times s (time of selling) follows b (time of buying).

-   No income taxes are assumed.

-   Besides the return derived from price change, there are other forms  of return of a asset arising during the time of investing. These  include airdrops, forks, rewards, burns and etc. All these must be  estimated as financial inflow or outflow per one unit of currency  (e.g. if while holding a position there is an airdrop of z amount  per unit, then this is a positive return of z).

![](/img/image14.png)

where:

Pi(s)- sell price at the discrete time s of asset i

Pi(b)- buy price at the discrete time B of asset i

Bi(t) -- quantified complimentary benefits of asset i for the period
between discrete times and b and s

K(s)- brokerage at the discrete time s

t -- discrete time of return.

 **Return of an investment portfolio **is calculated as a weighted average of the returns of all included assets. The weights correspond to the configuration of the portfolio -- the allocated investment in each position. The sum of all weights (including cash position) is always equal to 1. The return of a cash position is normally assumed 0.

![](/img/image15.png)

where:

Rp(t) -- return of the portfolio p at the discrete time t

Ri(t) -- return of the asset i at the discrete time t

wi(t) -- relative weight of position i at the discrete time t

There are several approaches to calculating **asset risk**. The dominant concept is to use variance and/or standard deviation and/or volatility
as a measure of risk. A good case could be built around using information entropy as a risk measure of a portfolio. So measuring the risk of an individual asset may be formulated as function of historical data of the return of asset:

![](/img/image16.png)

where:

Vi(t) -- risk of the asset i at the discrete time t

F -- function for measuring the risk of asset i

d -- number (depth) of historical data considered for calculation of
risk

No matter what measure is used for **portfolio risk**, there is a strong agreement among authors that "the risk of a portfolio is not a weighted
average of the risks of all included assets" (Jones, 1994, p. 573). The risk of a portfolio depends not only on the risks of every included asset, but also on the mutual dependence (interdependence) between and among the assets. Cash position is assumed to have a risk of 0. An example approach to measure portfolio risk is described below, where there are two additive terms -- one for weighted average of the risks of included assets and the other for calculating pair by pair the interdependence of the assets.

![](/img/image17.png)
where:

Vp(t) -- risk of the portfolio p at the discrete time t

Vi(t) -- risk of the asset i at the discrete time t

ρ(Vi(t),Vj(t))- measure for interdependence of the assets i and j at the discrete time t

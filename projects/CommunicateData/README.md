# Prosper Load Data Exploration
## by Vilija Vaitkeviciute


## Dataset

The loan data from [Prosper](https://www.prosper.com/), an online lending platform that connects people who want to borrow money with individuals and institutions, is explored here.  The loan data includes loan characteristics, Prosper's internal tracking data, borrower profile and some lender information.

There are 84,853 observations in the dataset (abreviated to include only post 13-July-2009 observations), where 13-July-2009 marks introduction of EstimatedReturn, EstimatedLoss, Estimated Yield, ProsperScore and other key variables to the analysis.

The dataset contains 81 features, of which majority are numerical (61), categorical (17) and boolean (3); some of the numerical variables are numerical categories or ratings (such as 'ProsperRating (numeric)', ListingCategory, ProsperScore).


## Summary of Findings

First, I narrowed down the variables analysed, having reviewed a complete correlation matrix (for numerical variables), and considered categorical variables separatelly.  These were the broad categories of variables analysed:

- EstimatedReturn components (estimates/actuals) ('EstimatedEffectiveYield', 'EstimatedLoss', 'LP_NetPrincipalLoss'),
- Borrower's current and historical need/utisation of credit facilities ('InquiriesLast6Months', 'CurrentDelinquencies', 'DelinquenciesLast7Years', 'BankcardUtilization', 'AvailableBankCardCredit'),
- Borrower's credit score as provided by external agencies ('CreditScoreRangeLower', 'CreditScoreRangeUpper'),
- Borrower's income profile ('DebtToIncomeRatio', 'StatedMonthlyIncome', 'MonthlyLoanPayment', 'IsBorrowerHomeowner'),
- Loan's properties ('LoanOriginalAmount', 'Term', 'ListingCategory (numeric)', 'LoanStatus') 
- date variables for time trends analysis, which in any, especially financial data is of importance ('ListingCreationDate', 'ClosedDate', 'LoanOriginationDate')
- categorical variables, which were not included in correlation analysis ('Occupation')
- variables that will need to be transformed, e.g because being abslute variables, perhaps could not have produced linear correlation with EstimatedReturns (e.g 'InvestmentFromFriendsAmount' and 'LoanOriginalAmount' can be used to calculate % of loan funded by friends)

## Key documents
> Full Analysis: `ProsperLoanDataAnalysis.ipynb` (and .html)

> Slide deck: `ProsperLoanAnalysisDeck.ipynb` (that can be rendered into html slide deck)

### Univariate analysis key findings

Note, this analysis was principally excluded from the slide deck, save for showing that dignificant number of observations did exist for meaningful analysis (i.e. sufficiently large sample sizes excpected after cutting into various subsets during analysis phase), the bivariate and multivariate analsis ultimatelly revealed very intersting observations; and structure of variables analysed can be seen in the bivariate and multivariate analysis.

Due to a large numberber of variables analysed, each variable's distribution was discussed separatelly near its individual chart in the detailed report 'ProsperLoanDataAnalysis.html'.

Large number of variables have a bell shaped distributions (including the dependent variables -- estimated returns, yield, loss -- and including independent variables of available bank credit (on log scale), borrower's credit score, debt to income ratio, stated monthly income and others), and majority have skewed distributions with long tails.  

The data contains outliers, including, but not limited to:
- negative yield loans, 
- some borrower's having made outsized number of inquiried in the last 6 months,
- some borrower's having outsized number of delinquencies,
- very large stated monthly incomes,
- very large available bankcard credit.
and generally many variables are skewed and have long tails.

Several variables are plotted on the log scale, due to existence of the long tails in their distribution, and the following variables:
- inquiries in the last six months, current and part 7 years delinquencies and bankcard credit availability.


### Bivariate analysis key findings

Analysis reveals that:

- For all 2009 loans and for large part of 2010 loans, estimated return did not include estimated loss , something that Prosper seems to have corrected in computing estimated returns in late 2010,
- Also from late 2010, estimated loss is (near perfect) linear function of estimated yield,
- Estimated yield (and loss) were lower in 2009 and 2010, then significant upward adjustment followed in 2011, following which, both have steadly declined, though the decline of estimated yield (from 2011 to 2014) was sharper than that of estimated loss in the same period,
- A single factor, that of credit score, appears to have strongest negative relationship with estiamted yield, in that higher credit score implies lower yields, which is intuitive,
- Many other factors have expected direction of correlation, but that it sometimes breaks down, and will warrant further investigation, for example:
  - Greater number of inquiries appears to correlate with higher estimated yields, but the direction of this relationship starts to break down (and is flat) from 6 enquiries onwards, and is reversed after 16 enquiries, which is counterintuitive.
  - Larger loans seem to be related to lower yields, and at first examination, larger loans in general are not issued to borrower's with low credit score, hence the lower yields.


### Multivariate analysis key findings

From 2011 to 2014, the estimated yields (and returns and losses) of loans have decreased each year (holding all risk factors constant), and that estimated returns would have decreased both as a result of reducing estimated yields, but also by slight increase in proportion applied to estimated loan losses (as proportion of yield).

Further, analysis highlighted that credit scores are particularly important when pricing loans, for example, it was evident that for low credit scores, loans will be associated with high yields, despite high available bank credit or low debt to income ratio. Credit score influence was throughout significant differentiator for loan pricing, including in loan sizes.


## Key Insights for Presentation

The analysis focuses on understanding how the lender's estimated returns relate to various factors, and how the estimated returns available from loans have evolved over time. 

The key insights are really inline with insights of the multivariate analysis, as this was the most in depth level of analsys, testing the relationships already gleamed/supposed following bivariate analysis.

What presentation attemps to show (given the analysis) is that from 2011 to 2014, the estimated yields (and returns and losses) of loans have decreased each year (holding all risk factors constant), and that estimated returns would have decreased both as a result of reducing estimated yields, but also by slight increase in proportion applied to estimated loan losses (as proportion of yield).

Further, analysis highlighted that credit scores are particularly important when pricing loans, for example, it was evident that for low credit scores, loans will be associated with high yields, despite high available bank credit or low debt to income ratio. Credit score influence was throughout significant differentiator for loan pricing, including in loan sizes.
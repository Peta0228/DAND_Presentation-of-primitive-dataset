# ProsperLoan Analysis, Bad Loan and Borrower APR 
## by Peter Wu

## Dataset

This dataset contains 113,937 loans with 81 variables on each loan, 
including loan amount, borrower rate, current loan status, borrower income, and many others. 
The dataset can be found in a 
repository for Amazon's AWS [here]( https://s3.amazonaws.com/udacity-hosted-downloads/ud651/prosperLoanData.csv),
with feature documentation available [here](https://www.google.com/url?q=https://docs.google.com/spreadsheet/ccc?key%3D0AllIqIyvWZdadDd5NTlqZ1pBMHlsUjdrOTZHaVBuSlE%26usp%3Dsharing&sa=D&ust=1554484977407000).

The goal of this analysis was set to determine two things:  first, which features are best at predicting the `LoanStatus`; second, which field best determine the `BorrowerAPR `  and  `BorrowerRate` at most?

## Summary of Findings

### In the exploration, several relationships were observed for the two pivot variables (`LoanStatus` and `BorrowerAPR`/`BorrowerRate`): 

 * There is a moderate negative raltionship between the `two credit score bounds` and  `BorrowerAPR`/`BorrowerRate`.
 
 * `ProsperScore` seemed to be negatively related to `BorrowerAPR`/`BorrowerRate`.
 
 * In high `ProsperScore`, the `BorrowerAPR`/`BorrowerRate` decreases as borrowers' `CreditScoreRangeLower` increases.
 
 * The **Defaulted**, **Cancelled**, **Chargedoff** and **Past Due**  `LoanStatus`, which all are bad loans, have a lower median `CreditScore Bounds` than the **Current** and **InProgress** LoanStatus, which are good loans (or about to be good loans). This might reveal that good debts came from a high credit score borrower on average.
 
 * If a loan was borrowed in a `Term` of ***36***, then it is more likely to go bad, if the borrower's `CreditScore` is below *700*.
 
 * If a borrower has a high `ProsperScore` of **11.0** and a high `CreditScoreRangeLower` above *700*, then his/her loan is almost guaranteed to not go bad.
 
 * Median and low `ProsperScore` (< **9.0**) in the `Term` ***36*** coontributed most to bad loans.
 
 ### Outside the main exploration, I had two interesting findings:
 
  * The two pairs of variables: `BorrowerAPR` and `BorrowerRate`, `CreditScoreRangeLower` and `CreditScoreRangeUpper` are almost perfectly related to each other. 
  *  There is also an interplay betweeen the two pivot variables,  although their relationships were not intended to be analyzed initially. 

## Key Insights for Presentation

For the presentation, I will focus my analysis on how `Credit Score`, `ProsperScore`, and  `Term`,  affect the pivot variables.

I will start with univariate analysis, looking at the distrbution of the three pivot variables: `LoanStatus`, `BorrowerAPR`, and `BorrowerRate`. Then shift to the bivaraite relationships between pivot variables and their potential determinants: `Credit Score`, `ProsperScore`, and  `Term`. Lastly, the multivariate section will dive deep into the interplays of each three variables. 

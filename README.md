# LAB2

In this lab, we analyzed and prepared the data, to be used in future methods. 
After extracting the macro categories for the economic sectors, we proceeded to Label Econcoding, using principalemnte two methodologies:
  1. Label Encoder used on 'TITOLOSTUDIO', 'MODALITALAVORO', 'PROVINCIAIMPRESA', 'ITALIANO'. 
  2. Encoding Manually Ordinal Categorical Features used only on GENERE, because the column has two distinct values (M and F, transformed into 0 and 1).

To verify the normal distribution of the data (Gaussian Distribution), we have applied the Shapiro-Wilk Test, which makes the data non-Gaussian. For this reason, non-parametric stastical methods should be used in the future. 

Before starting with the PCA, we check the original feature correlation. As we can see from the matrix, the highest correlation is between the Codice_ateco (which is the category of the economy sector) and the gender (male or female): it means that the sector in which a person can work, depend if you are a man or woman. 

To reduce the number of columns, we found component1 and component2 via PCA and saw the correlation they have with all of our columns. Here, we can see some correlations:
  - component1 with 'ANNO' and 'modalitalavoro_transformed'
  - component2 with 'ETA' and 'nazionalita_transformed'

We found outliers, such as a contract activated in 2201 and an age of 221. 
In addition, we also removed all those contracts entered into with people younger than 15 years old, because this is not allowed in Italy. 

For the seasonality, we can observe that in the month of August (in all years), the count of activated contracts drops drastically, while in the months of September and October, with the resumption of all work, contracts increase.

We check the stationarity and we notice that the mean is increasing, so the series is not stationary. Test Statistic is higher than the Critical Values.

Verify Forecastability of a Time Serie: Approximated Entropy and Sample Entropy are calculated. 
For the Approximated Entropy, if the value is close to 0, then the data is more predictable and therefore observable. this is the case for years.
otherwise, for the age, which has a value more distant from 0, we can say that it is not regular and predictable

Descriptive analysis: In this section, we consider only indeterminate contracts and analyze how this type is distributed across industries. 

Group by features given: The idea is to consider non-modifiable features for each person (gender, age, and nationality) and to target an indeterminated contract. The result, will be to get the best combination of all other features to get the contract.
The combination of age, gender and nationality which have the higest number of activated contract is a 30 years old man from Italy. 

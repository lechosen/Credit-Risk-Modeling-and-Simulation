# Credit Risk Modeling and Simulation

The code was to model credit-risky portfolios 1-year loss of corporate bonds under three different scenarios
– Monte Carlo Approximation 1 (5000 In-sample Scenarios, 1000 systemic scenarios and 5 idiosyncratic scenarios for each systemic, non-Normal distribution of losses); 
- Monte Carlo Approximation 2 (5000 In-sample Scenarios, 5000 systemic scenarios and 1 idiosyncratic scenario for each systemic, non-Normal distribution of losses);  
- rue Distribution (100000 Out-of-sample Scenarios, 100000 systemic scenarios and 1 idiosyncratic scenario for each systemic, non-Normal distribution of losses); 

The random variables to be generated in these case are the specific risk idiosyncratic factor and systemic risk credit drivers, which are consisted of the creditworthiness. 
<img width="862" alt="image" src="https://user-images.githubusercontent.com/90881469/190925645-28c079b2-9f46-4988-b806-14903f8c1803.png">
<img width="873" alt="image" src="https://user-images.githubusercontent.com/90881469/190925652-00449287-0518-4bb4-8c1b-33581550ab87.png">

In additional to analyze the sample error, the other purpose was to analyze the model error. Namely, tried to assume that each three sampling methods for the counterparty losses follow the Normal Distribution, whose formula is the following:
<img width="260" alt="image" src="https://user-images.githubusercontent.com/90881469/190925713-d45e6216-9f35-43bd-a413-d53842063b3b.png">

Lastly, computing the VaR and CVaR at 99.9% and 99% Quantile Levels for two types of portfolio (one is One unit invested for each 100 bonds and the other is Equal amount of dollar for each 100 bonds)

<img width="886" alt="image" src="https://user-images.githubusercontent.com/90881469/190925805-0db95ca8-e1b9-4d9b-bc4b-bb330ce1cd54.png">
<img width="949" alt="image" src="https://user-images.githubusercontent.com/90881469/190925840-bccd9484-79c6-4dba-8586-bad71e4c2d52.png">
<img width="946" alt="image" src="https://user-images.githubusercontent.com/90881469/190925852-a1f239eb-7ab5-47f7-b74a-e58015276fdb.png">

# Credit-Risk-Modeling-and-Simulation
1. Introduction
The code was to model credit-risky portfolios of corporate bonds under three different scenarios – Monte Carlo Approximation 1 (5000 In-sample Scenarios, 1000 systemic scenarios and 5 idiosyncratic scenarios for each systemic); Monte Carlo Approximation 2 (5000 In-sample Scenarios, 5000 systemic scenarios
and 1 idiosyncratic scenario for each systemic); True Distribution (100000 Out-of-sample Scenarios, 100000 systemic scenarios and 1 idiosyncratic scenario for each systemic); 

1.1 Study Data Introduction and Structural Model
The given instrument dataset contained the following values:
• Counterparty ID: total 100 counterparties (i.e., 100 corporate bonds in this study)
• Credit Risk Driver: each counterparty corresponds to different credit drivers (total 50 credit drivers)
• Credit State: Default; CCC; B; BB; BBB; A; AA; AAA (total 8 credit states)
• Probability: Chances of transitioning to each credit one year from now from current credit state
• Loss: The value-loss (positive numbers) result from the credit state transition. In case of default, the recovery rate has been taken into consideration

2 Method
2.1 Structural Model
The core part is to use structural model to calculate/simulate the random variable - creditworthiness, which is an index that infers a counterparty’s future credit state. The creditworthiness index (𝑤𝑗) involves two components: systemic risk credit drivers (𝑦𝑗) and specific risk idiosyncratic factor (𝑧𝑗). 𝑧𝑗 and 𝑦𝑗 are random variables to be generated to get the 𝑤𝑗. 𝑤𝑗 follows the below mathematical expression: 
𝑤𝑗=𝛽𝑗𝑦𝑗(𝑘)+𝜎𝑗𝑧𝑗 𝑤ℎ𝑒𝑟𝑒 𝑗 𝑖𝑠 𝑡ℎ𝑒 𝑐𝑜𝑢𝑡𝑒𝑟𝑝𝑎𝑟𝑡𝑦,𝑘 𝑖𝑠 𝑡ℎ𝑒 𝑐𝑟𝑒𝑑𝑖𝑡 𝑐𝑟𝑒𝑑𝑖𝑡 𝑑𝑟𝑖𝑣𝑒𝑟 𝑐𝑜𝑟𝑟𝑒𝑠𝑝𝑜𝑛𝑑𝑖𝑛𝑔 𝑡ℎ𝑒 𝑒𝑎𝑐ℎ 𝑐𝑜𝑢𝑛𝑡𝑒𝑟𝑝𝑎𝑟𝑡𝑦 𝑗
Explanation for each term:
• Creditworthiness 𝑤𝑗: infer the counterparty’s credit state in one year
• Sensitivity of counterparty 𝛽𝑗: given in the Section 1.1
• 𝜎𝑗=√1−𝛽𝑗2
• Systemic risk credit drivers (𝑦𝑗): a correlated random which requires the inputs from credit_driver_corr.csv file. To generate this random variable, it followed the below steps:
Step 1: Generate uncorrelated normal vectors A
Step 2: Obtain the covariance matrix from reading the credit_driver_corr.csv: 𝜌
Step 3: Decomposition 𝜌 into a matrix 𝐶𝐶𝑇=𝜌 using the Cholesky Decomposition
Step 4: Convert the uncorrelated vector A to correlated random variable 𝑦=𝐴∗𝐶
• specific risk idiosyncratic factor (𝑧𝑗): an uncorrelated random variable and follows the standard normal distribution (with mean is 0 and standard deviation 1). To generate this random variable, simply using np.random.randn in numpy library.

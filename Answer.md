## Question 1: ATE

### a) Linear Regression Estimates
Using the provided dataset, we obtain:
- Intercept (α) = 95.97
- Treatment Effect (τ) = -9.11
- Sustainability Spending Effect (β) = 1.51
- Model fit: R² = 0.6976

### b) ATE and Statistical Significance
The estimated Average Treatment Effect (ATE) is:
- **τ̂ = -9.11**

This suggests corporations participating in the carbon offset program (W=1) have engagement scores 9.11 points lower than non-participants (W=0), holding spending constant.

*Note: Statistical significance (p-value) cannot be determined from the given output. The exercise permits using Python/R - adding `statsmodels` would provide p-values.*

### c) Assumptions for Causal Interpretation

For the estimated treatment effect (τ̂ = -9.11) to represent a valid causal effect, the following conditions must hold:

1. **Conditional Exchangeability**  
   $$(Y^1, Y^0) \perp W \mid X$$  
   - Treatment assignment (W) is independent of potential outcomes after controlling for sustainability spending (X)  
   - *Implication*: No unmeasured confounders exist beyond X

2. **Consistency of Potential Outcomes**  
   $$Y = WY^1 + (1-W)Y^0$$  
   - The observed outcome equals the potential outcome under the actual treatment received

3. **Positivity**  
   $$0 < P(W=1|X=x) < 1$$  
   - All corporations have nonzero probability of being in either treatment group at their observed spending levels

4. **Correct Model Specification**  
   - The linear form $E[Y|W,X] = α + τW + βX$ correctly represents the data-generating process
   - *In your case*: Assumes no interaction between W and X

5. **SUTVA** (Stable Unit Treatment Value Assumption)  
   - No interference between corporations  
   - No hidden variations of the carbon offset program


## Question 2: Codespaces, Flask, & Docker
Tested using:

- `Wi = 1` (treated)
- `Xi = 20` ($20,000 spending)
### API test result:
```bash
{
  "w": 1.0,
  "x": 20.0,
  "predicted_engagement_score": 117.15789954894551,
  "intercept": 95.96616888130359,
  "treatment_effect (tau)": -9.10572148400991,
  "spending_effect (beta)": 1.5148726075825916
}
```

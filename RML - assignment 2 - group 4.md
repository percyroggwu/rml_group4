**RML \- Group Assignment 2 \- Proxy mismatch and optimization**

**Question A.**  
The efficiency axiom says that the sum of all Shapley values must equal the difference between the model’s prediction for one individual and the model’s average prediction across all individuals  
This means Shapley values are an accounting rule: together, they must fully explain why one prediction is above or below the average prediction.   
So if race has Shapley \= 0, it only means race added no extra contribution in that explanation relative to the average. It does not mean the model is blind to race or fully fair.

**Question B.**

**Model:** f(x) \= 1\[priors ≥ 3\], where x₁ \= race, x₂ \= prior arrests 

Since race never appears in f, ϕ\_race \= 0 for every instance by the dummy axiom.

Among non-recidivists, Black defendants have more prior arrests on average due to structural over-policing, so more cross the threshold and get falsely flagged as high risk:

* **Black FPR: 44.85%**  
* **White FPR: 23.45%**

ϕ\_race \= 0 throughout. However, Black defendants who did not reoffend were flagged at nearly twice the rate of white defendants. The bias does not disappear. It transfers into ϕ\_priors because prior arrests acts as a racial proxy. This is precisely how COMPAS operates, and why a zero Shapley value for race is not evidence of a fair model.

**Question C.**

1)No,  ϕ\_race \= 0 is not sufficient for fairness. It only shows that race does not directly contribute to the prediction for one individual.The other features in the model may have strong correlation with race, such as **priors\_count, charge\_degree, crime\_factor**. These features can act as proxies for race and still produce unequal outcomes across groups. Therefore ϕ\_race \= 0 does not guarantee the model is fair.

2)It would require both  ϕ\_race \= 0 and FPR parity under a high-stakes anti-discrimination governance framework, such as criminal justice. Because ϕ\_race \= 0 only explain race feasture does not contributes to an individual prediction and FPR parity checks whether one racial group is more likely to be falsely flagged than other groups. 

In the COMPAS, false positives can lead to serious unfair harm. 
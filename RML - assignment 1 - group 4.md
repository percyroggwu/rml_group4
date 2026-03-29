**RML \- Group Assignment 1 \- Proxy mismatch and optimization**  
**Group 4**

**Question A**

To verify the condition, we construct a numerical example where the values of U(h) decrease as L(h) increases, ensuring the affine relationship U(h)=a−b⋅L(h) holds. 

| Model | L(h) Loss functon  | U(h) human utility |
| :---- | :---- | :---- |
| A | 3 | 4 |
| B | 5 | 2 |
| C | 1 | 9 |

A formal condition is that the model with the lowest training loss is also the model with the highest human utility for all models under consideration.   
In other words, minimizing the loss must be equivalent to maximizing the true human objective. This can be represented with this formula:  
**U(h) \= a − b\*L(h)**  
**Human utility is inversely related to the loss**   
In our example, model C minimizes loss and maximizes human utility.

**Question B**

To construct an explicit counterexample where we again built the table with the numbers relevant to this case.

| Model | L(h) Loss functon  | U(h) human utility |
| :---- | :---- | :---- |
| A | 1(best) | 2( less utility) |
| B | 2 | 5(more utility) |
| C | 3(worst) | 1(less utility) |

As shown in model A, when the loss function is minimized, the human utility is not at its maximum. Model A achieves the best loss function 1 but only produces a human utility of 2\. In contrast, Model B has a higher loss value of 2 but holds a significantly greater human utility of 5\. This means that the superior model that offers human utility is Model B. Even though Model A produces the minimum loss function, we would be missing out on the greater human utility if we were to choose A. 

H={hA​,hB​,hC​}  
L(hA​)=1,L(hB​)=2,L(hC​)=3  
U(hA​)=2,U(hB​)=5,U(hC​)=1  
				

**arg min​ L(h) \= hA \-\> model A minimizes loss**  
**​while**  
**arg max​ U(h) \= hB​ \-\> model B maximizes utility**

**Question C**

Setting: HR area of a company that wants to implement a ML model that automated resume screening for job applicants giving them a score of how good a candidate is for a position.

| Component | Interpretation |
| :---- | :---- |
| H | Set of candidate screening/scoring models |
| L(h) | Proxy objective: Prediction error on historical hiring decisions |
| U(h) | Human objective: Actual long-term job performance and value of hired employees |

In this setting, the ML model is trained to minimize loss function L(*h*), which is the prediction error on historical hiring decisions. This means the model learns to replicate the patterns of past human hiring of the company. However, past hiring decisions may reflect human biases, such as favoring certain educational backgrounds, names, or characteristics that would be considered unrelated to actual job performance. 

The company risks automating and scaling historical bias if it optimizes only for L(h), rather than the true objective U(h).


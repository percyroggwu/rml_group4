**RML - Group Assignment 3 - Mathematical**

**Question 1**

Calibration within groups means that the same score should have the same meaning across groups. 

Formally:
P(Y=1 | S=s, A=0) = P(Y=1 | S=s, A=1), for every score level s.

if two people from different groups receive the same score, that score should represent the same probability of the outcome. For example, a score of 0.70 should imply about the same observed likelihood of Y=1 for both groups
FPR parity means equal false positive rates across groups. 

Formally:
P(h=1 | Y=0, A=0) = P(h=1 | Y=0, A=1).

This means that among individuals who truly belong to the negative class, both groups are incorrectly labeled as positive at the same rate. From a business perspective, this matters because it avoids one group being over-flagged, over-penalized, or more frequently denied by mistake
FNR parity means equal false negative rates across groups. 

Formally:
P(h=0 | Y=1, A=0) = P(h=0 | Y=1, A=1).

This means that among individuals who truly belong to the positive class, both groups are missed at the same rate. In practical terms, this matters when a model fails to identify deserving candidates, eligible customers, or truly risky cases unevenly across groups

**Question 2**

P(Y=1 | A=0) != P(Y=1 | A=1)
This means the real proportion of positive outcomes is different across groups. When this happens, a model cannot simultaneously satisfy calibration, equal FPR, and equal FNR, except in trivial cases.
Because if we force the model to have the same false positive rate and the same false negative rate in both groups, the meaning of a positive prediction will still change when the groups have different base rates. 

In other words, the same prediction will not represent the same real level of risk for both groups. That means calibration cannot also hold. Therefore, when base rates differ, no non-trivial classifier can satisfy calibration, FPR parity, and FNR parity at the same time.
same FPR + same FNR + different base rates -> different meaning of a positive prediction -> calibration fails


**Question 3**

The COMPAS are examples of the impossible result. The base rates differed from each group, COMPAS could not satisfy calibration, FPR parity, and FNR parity at the same time.
COMPAS was generally treated as being closer to calibration, meaning that the same risk score had a similar interpretation across groups. The lecture notes support this by showing that  Pr(Y=1∣R=s,G=Black)≈Pr(Y=1∣R=s,G=White), indicating that individuals with the same score had similar recidivism probabilities regardless of race, which is precisely the definition of calibration. 

However, it did not satisfy equal error rates, as it violated both FPR parity and FNR parity. Achieving equal FPR would require adjusting decision thresholds across groups, but doing so would change the interpretation of the same risk score and thus break calibration.

More specifically, Black defendants had a higher false positive rate, while White defendants had a higher false negative rate. This means COMPAS was more consistent with calibration, but it failed to achieve parity in error rates across groups.

**Question 4**

An organization should prioritize calibration over FPR parity when the model's output serves as decision support rather than an automated decision, when false negatives are more harmful than false positives, and when base rate differences between groups reflect genuine outcome differences rather than historical discrimination.

Governance Rule: Prioritize calibration when meaningful human oversight exists to catch false positives, and when accurate probability estimates matter more than equalizing error rates.
Burden-shifting justification: The burden-shifting framework asks who bears the cost of errors and whether that distribution is just. When a group shows a higher FPR, the burden shifts to the organization to justify it. Calibration provides that justification if the model is well calibrated, the higher FPR reflects a real base rate difference, not model bias. This is a defensible business necessity argument. 

However, this justification fails if the base rate difference itself stems from historical discrimination (e.g., over-policing inflating arrest rates). In that case, calibrating to those rates perpetuates injustice, and FPR parity should take priority instead — particularly in high-stakes, low-oversight settings like criminal justice or housing, where false positives impose severe, hard-to-reverse burdens on already-disadvantaged groups.

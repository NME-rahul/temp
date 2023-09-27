## Techniques to mine frequent patterns in data

1. Aprior algorithm
Employes bottom-up appraoch to discover frequnet itemset by first recognizing item and then looking for combinations of items that appear often together.

2. FP growth
It operates by building an FP-tree, which is a compact repersentation of the dataset. The Fp-tree construct patterns from ground to up. efficent then other alforithms.

3. Closed frequent itemset
In this technique, all frequent itenset in a give dataset with a frequncy that meets or exceeds a predetrmined threshold are discoverd.The technique works by first generating a list of all frequent item sets in the dataset, then iteratively evaluating each item set to determine whether any supersets of the itemset have a frequency that meets or exceeds the stated threshold. Any supersets that meet the criteria are added to the list of frequently occurring itemsets. This procedure is continued until no further supersets are discovered.

4. Naive Bayesian Algorithm
It uses Bayes theorem, that predicts each attribute's class using it's probability.
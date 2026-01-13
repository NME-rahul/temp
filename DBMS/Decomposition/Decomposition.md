# Decompositions
1. Lossy DEcomposition
2. Lossless Decomposition

let `R(r1, r2, r3, ..., rn)` is a relation having attributes $r1, r2, r3, ...., rn$

For every decomposition

$$R \supseteq r1 \bowtie r2 \bowtie r3 \bowtie ..... rn $$


## 1. Lossy Decomposition
$$R \supset r1 \bowtie r2 \bowtie r3 \bowtie ..... rn $$

The word loosy refers to loose of information not the tuples, if we losse the information after decomposition then it is called lossy decomposition, remember we can can get some extra tuples called suprious tuples after joining decomposed relations not less tuple.


## 2. Lossless Decomposition/Non-addititve decomposition

$$R = r1 \bowtie r2 \bowtie r3 \bowtie ..... rn $$

If we don't losse any information due to decomosition and get the same relation after natural join then it is called lossless decomposition. we should not have extra tuples but exatly the same number of tuple.

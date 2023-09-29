## Measuring Data similarity and dissimilarity

### Similarity Measure

A similarity measure is a mathematical functions that quantifies the degree of similairty between data points. it is a numerical score measuring how alike two data points are.


### Dissimilarity Measure

Dissimilairty measures are used to quantify the degree of difference or distance between two objectas data points. it can be measure as inverse of similarity score. if using a tecnique generate high score for strong relationship then low score will show the weaker relationship and vice versa.


**Measusring technique**

1. Cosine similarity

		COS(\theta) = \frac{A.B}{ |A||B|}

2. Euclidean distance

		d = \sqrt{ (x_2 - x_1)^2 + (y_2 - y_1)^2}

3. Manhatten distance

		d = \sum_{i=0}^{n}|x_i - y_i|

4. Pearson correlation coefficeint

		r = \frac{cov(x, y)}{\sigma_x . \sigma_y}

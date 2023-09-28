Basket 1: Bread, Milk, Eggs

Basket 2: Bread, Diaper, Beer, Milk

Basket 3: Bread, Milk, Diaper, Soda

Basket 4: Milk, Diaper, Beer, Chips

Find the bayesian belief itemset {Bread, Milk} with item Eggs

---


1. Prior probaility

* assume prior probaility, there are 20% chance that customer will buy {Eggs} with {Bread, Milk}.
* probability if X
	
		p({Bread, Milk}) = 3/4 = 0.75


2. likelihood
	
		p(X,Y) = number of transcation in which both itemset(X,Y) itemsetoccured / total transaction

* find the probability of {Bread, Milk} and {Eggs}

		p({Bread, Milk, Eggs}) = 1 / 4 = 0.25

3. Marginal probabilty

		p(X,Y) = number of transcation in which both itemset Y occured / total transaction

* probailty of buying Eggs.

		p({Eggs}) = 1/4 = 0.25

4. Bayesian Belief

		p(Y/X) = p(X, Y) * p(X) / p(Y)

		p({Eggs}/{Bread, Milk}) = p({Bread, Milk, Eggs}) * p({Bread, Milk}) / p({Eggs}) =  (1/4) * (3/4) / (1/4) = 3/4

	

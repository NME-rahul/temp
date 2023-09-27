# Data object
* it refers to an instance of a data structure or a container that holds information or data.
* Dataset defining a defining a set of atributes is called data object.
* if data is structured in row and column form then row refers to the object.

# Data atribute
* in database, atributes refers to the characteristics or properties that describes an entity or object. this are also known as fileds, columns or variables, depneding on the context.


# Association rule
* Association rule is a data mining technique used to discover interesting relationship, paterns or associatio in large dataset. for example it is commonly used in market basket analysis to find relationship in between different products.

1. Support: Measures the frequency of a particular itemset in the dataset. it tells us how often an itemset is occuring in basket.
		
			Supp(X) = Freq(X) / total transaction
			Supp(X,Y) = Freq(X,Y) / total transaction
		
2. Confidence: Measures the probability that if a basket contains item A, it also contains item B. It indicates how often item B is bought when item A is bought.
			
		Conf({X}->{Y}) = Freq(X,Y) / Freq(X)
	
3. Lift: Measures the strength of association between two items. it tells us how more likely item B is bought when item A is bought compared to if they were bought independently
		
		Lift = Supp(X,Y) / Supp(x) * Supp(y)

eg.

	Basket 1: Bread, Milk, Eggs
	Basket 2: Bread, Diaper, Beer, Milk
	Basket 3: Bread, Milk, Diaper, Soda
	Basket 4: Milk, Diaper, Beer, Chips

Find the association of itemset {Bread, Milk} with item Eggs

1. find support

		total basket(transaction) = 4
		
		Supp(X) = transaction containg X / Total transcation
		
		support({Bread, Milk}) = 3/4


2. Confidence

		Conf({X}->{Y}) = Transcation containing X and Y / Transaction containing itemset X
		
		Conf({Bread, Milk}->Eggs) = 1/3 = 0.33

3. Lift

		Lift({X}->{Y}) =  Supp(X,Y) / Supp(X) * Supp(Y)
		
		Lift({Bread, Milk}->Eggs) = 1 / 3*1 = 0.33
		
		
		The grater the value of confidence level the grater relation have in between itemset.
		Lift = 1, indicates X and Y almost often appear together as expected
		Lift > 1, means they appear together more then expected. 
		Lift < 1, means they appear less than expected.



		X={Bread, MilK}
		Y={Diaper}

1. Supp(X)

		Supp({Bread, MilK}) = 3/4 = 0.75
		
		Supp({Diaper}) = 3/4 = 0.75
		
		Supp(X,Y) = 2/4 = 0.5

2. Conf(X->Y)

		Conf({Bread, MilK}->{Diaper}) = 2/3

3. Lift

		Lift({Bread, MilK}->{Diaper}) = Supp(X,Y) / Supp(X) * Supp(Y) = 0.5/0.75*0.75 = 0.89




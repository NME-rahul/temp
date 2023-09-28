### Frquent itemset
* A frequent itemset is a set of items that occur together frequently in dataset.
for example : 
analysis of banking data
corss-marketing
catalog design

---

### Closed itemset
* Aa closed itemset is a set of itemset that is not included in any other set with the same support. in other words closed itemset is a frequnt itemset that is not included in the superset with same support.


##  Frequent Itemset Mining Methods
### Apriori algorithm
*  It is primarily used for discovering frequent itemsets within transaction databases and generating association rules based on those frequent itemsets. 

        Transaction 1: Bread, Milk
        Transaction 2: Bread, Diapers, Beer, Milk
        Transaction 3: Bread, Milk, Diapers, Soda
        Transaction 4: Milk, Diapers, Beer, Chips
        Transaction 5: Bread, Milk, Beer

threshold support values minSupport = 0.5

Step1: Count the frequency in dataset or support for each item

    Supp(Bread) = 4/5 = 0.8
    Supp(Milk) = 5/5 = 1
    Supp(Diaper) = 3/5 = 0.6
    Supp(Beer) = 3/5 = 0.6
    Supp(Soda) = 1/5 = 0.2
    Supp(Chips) = 1/5 = 0.2

Step2(Join): join two items having support grater and equal to threshold

    {Bread, Milk} 
    {Bread, Diaper}
    {Bread, Beer}
    {Milk, Diaper}
    {Milk, Beer}
    {Diaper, Beer}


Step3(Prune): again find support for each itemset and prune/remove the itemset that have support value less then minSupport value

    Supp({Bread, Milk}) = 4/5 = 0.8
    Supp({Bread, Diaper}) = 2/5 = 0.4
    Supp({Bread, Beer}) = 2/5 = 0.4
    Supp({Milk, Diaper}) = 3/5 = 0.6
    Supp({Milk, Beer}) = 3/5 = 0.6
    Supp({Diaper, Beer}) = 2/5 = 0.4

    after pruning:-
    Supp({Bread, Milk})
    Supp({Milk, Diaper})
    Supp({Milk, Beer})

step4: now apply association rule on these itemset after pruning

    Supp({Bread, Milk}->{Diaper}) = 2/5 = 0.4
    Supp({Bread, Milk}->{Beer}) = 1/5 = 0.2
    Supp({Milk, Diaper}->{Beer}) = 2/5 = 0.4
    
    Conf({Bread, Milk}->{Diaper}) = Freq(X,Y)/Freq(X) = 2/4 = 0.5
    Conf({Bread, Milk}->{Beer}) = Freq({Bread, Milk}->{Beer})/Freq({Bread, Milk}) = 1/4 = 0.25
    Conf({Milk, Diaper}->{Beer}) =  2/3 = 0.67
    
    Lift({Bread, Milk}->{Diaper}) = Supp(X,Y)/Supp(X) * Supp(Y) = 0.4/0.4*0.6 = 1.67
    Lift({Bread, Milk}->{Beer}) = 0.2/0.8*0.6 = 0.41
    Lift({Milk, Diaper}->{Beer}) = 0.4/0.6*0.6 = 1.11


conclsion:
Items {Bread, Milk, Diaper} and {Milk, Diaper, Beer} are expected to sells together so put the their stalls together.
Item {Bread, Milk, Beer} are not expected to sell together.

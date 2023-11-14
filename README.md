# Association-Rule-Apriori

In this ipynb code we have uploaded a csv file which have rows containing the values of 
products that are usually bought together 
* example -
  Left Hand Side |	Right Hand Side	 |  Support	 |  Confidence	 |  lift
  light cream    |	chicken	         |0.004533	 |0.290598	     | 4.843951

In this example we see that the Light cream and the chicken is usually bought together which show the confidence of 0.290598 

IN DETAIL
Apriori Algorithm 
Step - 1 :- Set a Minimum aupport and confidence 
Step - 2 :- Take all the subset in Transactions having higher support than Minimum Support 
Step - 3 :- Take all the rules of these subsets having higher confidence then Minimum Confidence 
Step - 4 :- Sort the rules by Decreasing Lift 

*Suppose we have Item sets that are usually bought together 

ID  |  Item set 
1   |  mineral water, olive oil, Wine, pancakes, green grapes, yams
2   |  Dates, Olive, Wine, Pancakes, green grapes, yams
3   |  mineral water, Avacado, Pancake, green grapes
4   |  mineral water, Juice, cottage cheese, pancakes, yams
5   |  cottage cheese, olive oil, olive oil, pancakes, green grapes

Support count of each item set

Items           |  Count

Mineral Water   |   3
Olive oil       |   4
Wine            |   2
green grapes    |   4
yams            |   3
Dates           |   1
Avacado         |   1
Juice           |   1
cottage cheese  |   2
Pancakes        |   5

We will set minimum support of 60%
which is  = 60/100*5 = 3 , 5 is number of total transactions 

We have categorised all items above 3 

Items           |  Count
                                                            
Mineral Water   |   3
Olive oil       |   4
Pancakes        |   5
green grapes    |   4
yams            |   3

Now will make pairs for each item with every item like 
Mineral Water, Olive oil = 1
Mineral Water, Pancakes = 3
Mineral Water, green grapes = 2
Mineral Water, Yams = 2
Olive oil, Pancakes = 3
Olive oil, green grapes = 3
Olive oil, yams = 2
Pancakes, green grapes = 4
Pancakes, yams = 3
green grapes, yams = 2

Among this we will categorise all above 3 

Mineral Water, Pancakes = 3
Olive oil, Pancakes = 3
Olive oil, green grapes = 3
Pancakes, green grapes = 4
Pancakes, yams = 3

Item Pair all the the item occurance with 3 Like using the above data

Mineral Water, Olive oil, Pancakes  -  1
Mineral Water, Pancakes, green grapes - 2
Mineral Water, Pancakes, Yams - 2
Olive oil, Pancakes, green grapes - 3
Pancakes, green grapes, yams - 2

The Highest Number in this is 3 so we will be using 
Olive oil, Pancakes, green grapes - 3

Association Rule                         Support        Confidence      Confidence
Olive Oil ^ Pancakes = Green Grapes  =      3                3/3            100
Olive Oil ^ Green Grapes = Pancakes  =      3                3/3            100
Pancakes ^ Green Grapes = Olive Oil  =      3                3/4            75

If the Minimum Confidence is set to 80% Then according to the data above we will choose only 
Olive Oil ^ Pancakes = Green Grapes  =      3                3/3            100
Olive Oil ^ Green Grapes = Pancakes  =      3                3/3            100

Which gives a 100% Confidence that this products are bought together 

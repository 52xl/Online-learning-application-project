# Online-learning-application-project
Imagine an ecommerce website which can sell an unlimited number of units of 5 different
items without any storage cost.
In every webpage, a single product, called primary, is displayed together with its price. The
user can add a number of units of this product to the cart. After the product has been added
to the cart, two products, called secondary, are recommended. When displaying the
secondary products, the price is hidden. Furthermore, the products are recommended in two
slots, one above the other, thus providing more importance to the product displayed in the
slot above. If the user clicks on a secondary product, a new tab on the browser is opened
and, in the loaded webpage, the clicked product is displayed as primary together with its
price. At the end of the visit over the ecommerce website, the user buys the products added
to the cart.
We assume that the user has the following behavior:
 she/he buys a number of units of the primary product if the price of a single unit is
under the user’ reservation price; in other words, the users’ reservation price is not
over the cumulative price of the multiple units, but only over the single unit;
 once the primary product has been bought, the user clicks on a secondary product
with a probability depending on the primary product except when the secondary
product has been already displayed as primary in the past, in this case the click
probability is zero (thus, in practice, excluding the case in which a product is
displayed as primary more than once --- as a result the number of webpages visited
by the user is finite);
when observing the secondary products, the user initially observes the first slot and,
after having observed that slot, observes the second slot. Assume that the probability
with which the first slot is observed is 1, while the probability with which the second
slot is observed is lambda < 1. The value of lambda is assumed to be known in all
the three project proposals.
Notice that the probability of a click on a secondary product depends on:
 the purchase probability of the primary product,
 the probability to observe the slot in which the secondary product is displayed, and
the click probability of the secondary product conditioned to the purchase of the
primary.


* ## Step 1 Enviroment
 Develop the simulator by Python.  imagine a motivating
application and specify an opportune choice of the probability distributions associated with
every random variable. Moreover, assume that there are 2 binary features that define 3
different user classes. The users’ classes potentially differ for the demand curves of the 5
products, number of daily users, 𝛼 ratios, number of products sold, and graph probabilities.
That is, for every random variable, that need to be provided to the three different distributions, each one
corresponding to a different users’ class.

* ## Step 2 Optimization algorithm
Formally state the optimization problem where the objective
function is the maximization of the cumulative expected margin over all the products. Design
a greedy algorithm to optimize the objective function when all the parameters are known.
The algorithm works as follows. At the beginning, every item is associated with the
corresponding lowest price. Then, evaluate the marginal increase obtained when the price of
a single product is increased by a single level, thus considering 5 potential different price
configurations at every iteration, and choose the price configuration providing the best
marginal increase (a price configuration specifies the price of every product). The algorithm
stops when no new configuration among the 5 evaluated is better than the previous one. For
instance, at the beginning, evaluate the 5 price configurations in which all the products are
priced with the lowest price except for one product which is priced with the second lowest
price. If all these price configurations are worse than the configuration in which all the
products are priced with the lowest price, stop the algorithm and return the configuration with
the lowest price for all the products. Otherwise, choose the best price configuration and
re-iterate the algorithm. Notice that the algorithm monotonically increases the prices as well
as the cumulative expected margin. Therefore, the algorithms cannot cycle. However, there
is not guarantee that the algorithm will return the optimal price configuration. 

* ## Step 3 Optimization with uncertain conversion rates.
Focus on the situation in which the binary features cannot be observed and therefore data are aggregated. 
Design bandit algorithms (based on UCB and TS) to face the case in which the conversion rates are
unknown.

* ## Step 4 Optimization with uncertain conversion rates, 𝛼 ratios, and number of items sold perproduct.
 same of Step 3 when also the alpha ratios and the number of items sold per
product are uncertain.

* ## Step 5 Optimization with uncertain graph weights.
 Do the same as Step 3 when the uncertain parameters are the graph weights. Develop the algorithms 
 and evaluate their performance when applied to the simulator.

* ## Step 6 Non-stationary demand curve.
Now assume that the demand curves could be
subjected to abrupt changes. Use a UCB-like approach with a change detection algorithm to
face this situation and show whether it works better or worse than using a sliding-window
UCB-like algorithm. 

* ## Step 7 Context generation.
same of Step 4 when the features can be observed by
the ecommerce website. For simplicity, run the context-generation algorithms only every 2
weeks. When we have multiple contexts, the prices of each single context can be chosen
and thus optimized independently of the others. 




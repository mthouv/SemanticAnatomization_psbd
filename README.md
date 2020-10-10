# Knowledge Graph Anonymization using Semantic Anatomization

The goal of is this repo is to provide complementary information for our paper "Knowledge Graph Anonymization using Semantic Anatomization" submitted to the 7th International Workshop on Privacy and Security of Big Data.


## Directory "queries"
It contains the different queries mentionned in the article:
* *query_inital_cluster* corresponds to the query referenced in section 4.3 allowing us to retrieve the initial clusters used in our algorithm
* *query_update* corresponds to the query referenced in section 4.5 allowing us to insert intermediary nodes between the EoIs and the SAs.

## Algorithm
Here we provide the pseudo-code for the algorithm described in section 2.

![](algo/algo.JPG)


## Religion ontology

This is the 4-level hierarchy we used to extend our LUBM datasets

![](onto/religion.png)


## Evaluation

We provide the effectiveness results presented in the paper in section 6
We also added the results of our comparison with a state-of-the art suppression-based technique.
Finally, we present several tables summarizing the execution times of our approach with complementary results computed from smaller datasets.

### Effectiveness to anwser counting queries

Two attributes / One sensitive attribute

![](results/relative_error/relative_error_2_1.jpg)

Two attributes / Two sensitive attributes

![](results/relative_error/relative_error_2_2.jpg)

Three attributes / One sensitive attribute

![](results/relative_error/relative_error_3_1.jpg)

Three attributes / Two sensitive attributes

![](results/relative_error/relative_error_3_2.jpg)

Four attributes / One sensitive attribute

![](results/relative_error/relative_error_4_1.jpg)

Four attributes / Two sensitive attributes

![](results/relative_error/relative_error_4_2.jpg)


### Comparison with a suppression technique: Query-based linked data anonymization by Delanaux et al.

2 attributes

![](results/delanaux_relative_error/eval_delanaux_2.jpg)

3 attributes

![](results/delanaux_relative_error/eval_delanaux_3.jpg)

4 attributes

![](results/delanaux_relative_error/eval_delanaux_4.jpg)


In a generalization/suppression context, we can only assume a uniform distribution for the values of the sensitives attributes. Hence, in the above-figures, we can see that the technique performs well when the values are indeed uniformly distributed but fails to provide satisfiable results otherwise.

### Execution times


*HasReligion* predicate

![](results/exec_times/execution_time_hasReligion.JPG)


*Advisor* predicate

![](results/exec_times/execution_time_advisor.JPG)


Since our approach is primarily dependent on the number of distinct values for the SA rather than the size of the graph, we observe constant and relatively low execution times for the *hasReligion* predicate.

On the other hand, tho objects for the *advisor* predicate being professor nodes, the number of distinct values grows with the size of the graph thus the execution times grow as well.
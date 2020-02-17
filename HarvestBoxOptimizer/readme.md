# Example: Harvest Box Optimizer

You are a data scientist at a company delivering boxes of vegetables to customers. Write an algorithm that takes into account your inventory, orders, and if known, the customer’s preferences, and create boxes out of the food you have.

![harvest box optimization problem statement](images/harvest_box_optimizer.png "Harvest Box Optimization Problem Statement")

## Data

You have the following data to work with

**Orders**:
- `client name`
- `date`

**Order history**:
- `date`
- `box contents`

**Client preferences**:
- `likes`
- `dislikes`

**Inventory**:
- `type`
- `weight`
- `volume`
- `best by date`

**Recipes**
- `ingredients list`

## Questions

In order to guide the formulation of an optimization problem, it can be helpful to ask yourself a few questions first:

* Q 0: What does a solution look like?

Given each individual box (to be sent to a given customer), and each individual item in our inventory, a solution could take the form of a yes/no (1 or 0) whether this item should go into that box.


Example:
\begin{equation}
X_{b, i} \in \{0, 1\} \qquad \text{for all } b\in \text{ boxes  and } i\in \text{ items}
\end{equation}

Here, if $X_{b, i} = 1$, this means that item $i$ is assigned to box $b$. Conversely, if $X_{b, i} = 0$, item $i$ is not going into box $b$.


* Q 1: What are we trying to optimize for?

Think of something we may want to optimize for (something our solution should maximize or minimize). It should be something that our data above can capture. Can you describe it and come up with a formula?

Example: Send customers things that they like

* Q 2: Can you think of any constraints?

Examples:
1. We cannot use more potatoes than we have in our inventory.
1. If we know the maximum volume and weight each box can carry, we cannot exceed that when deciding how much to put in each box

* Q 3: If you had a database of recipes, how could you use them to simplify your problem

Remember: each recipe has a list of ingredients...


* Q 4: How might different food products’ shelf life be relevant for this problem?


Can you come up with a cost or constraint that ensures we don't have to throw out produce?


Example: Minimize the number of vegetables that will go out of date (by ensuring we use up inventory that has the soonest best by date first)


* Q 5: What would change if some of the orders haven't been placed yet, but you have forecasts of what they might be?

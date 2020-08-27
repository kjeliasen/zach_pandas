# Advanced Pandas Exercises

In here you'll find a sqlite database and a bunch of questions about the data
within it.

## Orientation

Get familiar with the pizza database. This database contains information about a
number of orders from a pizza delivery store.

### SQLite Quickstart

The database is a [sqlite database](https://sqlite.org/index.html). If you have
anaconda installed, you can explore the database and write SQL queries against
it by running:

```
sqlite3 pizza.sqlite
```

If you've never used sqlite before, you may wish to run these 2 commands for
more friendly output:

```
.headers on
.mode column
```

To list all the tables in the database:

```
.tables
```

For more help with sqlite commands, run:

```
.help
```

From here you can start running queries on the database:

```
SELECT * FROM pizzas LIMIT 5;
```

### Getting the Data Into Pandas

The `sqlite3` module is part of the python standard library, so you shouldn't
need to install anything.

```python
import pandas as pd
import sqlite3

connection = sqlite3.connect('pizza.sqlite') # or specify the path to the db file

pizzas = pd.read_sql('SELECT * FROM pizzas', connection)
```

## Questions

- What information is stored in the `toppings` table? How does this table relate
  to the `pizzas` table?
- What information is stored in the `modifiers` table? How does this table relate
  to the `pizzas` table?
- How are the `pizzas` and `sizes` tables related?
- What other tables are in the database?
- How many unique toppings are there?
- How many unique orders are in this dataset?
- Which size of pizza is sold the most?
- How many pizzas have been sold in total?
- What is the most common size of pizza ordered?
- What is the average number of pizzas per order?

---

Find the total price for each order. The total price is the sum of:

- The price based on pizza size
- Any modifiers that need to be charged for
- The sum of the topping prices

Topping price is affected by the amount of the topping specified. A light amount
is half of the regular price. An extra amount is 1.5 times the regular price,
and double of the topping is double the price.

---

- What is the average price of pizzas that have no cheese?
- What is the most common size for pizzas that have extra cheese?
- What is the most common topping for pizzas that are well done?
- How many pizzas are only cheese (i.e. have no toppings)?
- How many orders consist of pizza(s) that are only cheese? What is the average
  price of these orders? The most common pizza size?
- How may large pizzas have olives on them?
- What is the average number of toppings per pizza?
- What is the average number of pizzas per order?
- What is the average pizza price?
- What is the average order total?
- What is the average number of items per order?
- What is the average number of toppings per pizza for each size of pizza?
- What is the average order total for orders that contain more than 1 pizza?
- What is the most common pizza size for orders that contain only a single
  pizza?
- How many orders consist of 3+ pizzas? What is the average number of toppings
  for these orders?
- What is the most common topping on large and extra large pizzas?
- What is the most common topping for orders that consist of 2 pizzas?
- Which size of pizza most frequently has modifiers?
- What percentage of pizzas with hot sauce have extra cheese?
- What is the average order price for orders that have at least 1 pizza with
  pineapple?

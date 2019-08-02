# Crowdfunding SQL

## Learning Goals

* Identify table example  
* Create a new table, records, and queries

## Identify Table Example

`SQL` is a programming language that allows you to "nest" statements inside each
other. Let's quickly take a look at an example of that does this with grocery
data.

### Create a Grocery Table

```sql
CREATE TABLE groceries (id INTEGER PRIMARY KEY, name TEXT, quantity INTEGER, aisle INTEGER);

INSERT INTO groceries VALUES (1, "Apples", 2, 1);
INSERT INTO groceries VALUES (2, "Oranges", 4, 2);
INSERT INTO groceries VALUES(3, "Peaches", 6, 3);
```

### Grocery Schema

```text
id                 name        quantity      aisle
------------    ----------  ----------  ----------  
1                Apples          2          1
2                Oranges         4          2
3                Bananas         6          3
```

### `SUM`

`SUM` will return the total of the column you select. In this case, the total
number of items in the `groceries` column is 12.

```sql
SELECT SUM(quantity) FROM groceries;
```

### Returns

```sql
SUM(quantity)
-------------
12
```

To make it a little more useful we can `GROUP BY` the aisle that the items are
in and `ORDER BY` the sum of the `aisle`.

```sql
SELECT aisle, SUM(quantity) FROM groceries GROUP BY aisle ORDER BY SUM(quantity);
```

### Returns

```sql
aisle    SUM(quantity)
-------  --------------
1           2
2           4
3           6
```

## Create New Table, Records and Queries

Now we're going to create a schema based on the following information:

* A project has a title, a category, a funding goal, a start date, and an end date.
* A user has a name and an age
* A pledge has an amount. It belongs to a user, and it also belongs to a project.

### Create the Tables

In the `create.sql` file, model your tables. You should have a table for
projects, users, and pledges.

### Insert Records into Database

Within the `insert.sql` file, insert 10 projects, 20 users, and 30 pledges into the database.

### Write the Queries

Write the following queries in SQL. You'll use different kinds of SQL joins to
arrive at the answers for most. Write your queries in the `lib/sql_queries` file
like the example below:

```ruby
def select_category_from_projects
  "SELECT category FROM projects;"
end
```

## Resources

* [Seldom Blog](http://blog.seldomatt.com/) - [About SQL Joins: The 3 Ring Binder Model](http://blog.seldomatt.com/blog/2012/10/17/about-sql-joins-the-3-ring-binder-model/)
* [Coding Horror](http://blog.codinghorror.com/) - [A Visual Explanation of SQL Joins](http://blog.codinghorror.com/a-visual-explanation-of-sql-joins/)
* [Geeky is Awesome](http://geekyisawesome.blogspot.com/) - [SQL Joins Tutorial](http://geekyisawesome.blogspot.com/2011/03/sql-joins-tutorial.html)

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/sql-crowdfunding-lab' title='SQL Crowdfunding Lab'>SQL Crowdfunding Lab</a> on Learn.co and start learning to code for free.</p>

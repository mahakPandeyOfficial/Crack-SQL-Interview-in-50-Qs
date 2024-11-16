# SQL Query Solution

## Problem Statement
Given a **Customer** table with the following columns:
- `id` - the ID of each customer.
- `name` - the name of each customer.
- `referee_id` - the ID of the referee who referred this customer, which can also be `NULL` if the customer has no referee.

Write an SQL query to find the names of customers who:
1. Do not have a referee with `referee_id` equal to 2, or
2. Have a `NULL` value in the `referee_id` column (indicating no referee).

👉 [View the solution on LeetCode](https://leetcode.com/problems/find-customer-referee/solutions/6049219/my-sql-solution-with-handling-null-cases)

## Solution Explanation

### Intuition
To find the required customers, we need to filter based on the `referee_id` values:
1. Customers whose `referee_id` is not equal to 2.
2. Customers whose `referee_id` is `NULL`.

We can use the logical `OR` operator to combine these two conditions, allowing us to select customers who meet either criterion.

### Approach
1. Use the `SELECT` statement to retrieve the `name` column from the **Customer** table.
2. In the `WHERE` clause, set two conditions:
   - `referee_id != 2`: Filters for customers with a referee ID other than 2.
   - `referee_id IS NULL`: Filters for customers who have no referee (i.e., `referee_id` is `NULL`).
3. Use the `OR` operator to combine these conditions, so we get customers that satisfy either of them.

### Complexity
- **Time Complexity**: $$O(n)$$, where $$n$$ is the number of rows in the **Customer** table, as each row needs to be checked for the conditions.
- **Space Complexity**: $$O(m)$$, where $$m$$ is the number of rows that meet the conditions and are included in the output.

## Solution Code

```mysql
# Write your MySQL query statement below
SELECT name 
FROM CUSTOMER 
WHERE referee_id != 2 OR referee_id IS NULL;

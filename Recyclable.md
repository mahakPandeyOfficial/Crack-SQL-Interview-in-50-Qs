# SQL Query Solution

## Problem Statement
Given a **Products** table with the following columns:
- `product_id` - the ID of each product.
- `low_fats` - a character column (`Y` or `N`), indicating whether the product is low-fat.
- `recyclable` - a character column (`Y` or `N`), indicating whether the product is recyclable.

Write an SQL query to find the IDs of products that are both low-fat and recyclable.

👉 [View the problem  & Solution on LeetCode](https://leetcode.com/problems/recyclable-and-low-fat-products/solutions/6049399/mysql-solution-easy)

## Solution Explanation

### Intuition
We need to filter the products to get only those that meet both conditions: 
1. `low_fats` should be `'Y'` (indicating the product is low-fat).
2. `recyclable` should be `'Y'` (indicating the product is recyclable).

Using the logical `AND` operator will allow us to select products that satisfy both of these conditions.

### Approach
1. Use the `SELECT` statement to retrieve the `product_id` column from the **Products** table.
2. In the `WHERE` clause, add two conditions:
   - `low_fats = 'Y'`: Filters for products that are low-fat.
   - `recyclable = 'Y'`: Filters for products that are recyclable.
3. Combine the conditions with the `AND` operator so only products that are both low-fat and recyclable are selected.

### Complexity
- **Time Complexity**: $$O(n)$$, where $$n$$ is the number of rows in the **Products** table, as each row needs to be checked for the conditions.
- **Space Complexity**: $$O(m)$$, where $$m$$ is the number of rows that meet both conditions and are included in the output.

## Solution Code

```mysql
# Write your MySQL query statement below
SELECT product_id 
FROM Products 
WHERE low_fats = 'Y' AND recyclable = 'Y';
```

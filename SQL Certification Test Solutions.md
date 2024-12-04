**Question 1:**

Write an SQL query to fetch the product IDs and names of products from the "Electronics" category that are priced above $1000.

**Answer:**

```sql
SELECT p.product_ID, p.name
FROM product_information p
JOIN pricing_details d
ON p.product_ID = d.product_ID
WHERE p.category = 'Electronics' AND d.price > 1000;
```

**Explanation:**

- **`SELECT p.product_ID, p.name`:** Specifies that we need the product ID and name of the products.
- **`FROM product_information p`:** Fetches data from the `product_information` table.
- **`JOIN pricing_details d ON p.product_ID = d.product_ID`:** Joins the `product_information` table with the `pricing_details` table using the common column `product_ID`.
- **`WHERE p.category = 'Electronics' AND d.price > 1000`:** Filters the results to include only products in the "Electronics" category priced above $1000.

**Result:**

- A list of product IDs and names from the "Electronics" category with prices exceeding $1000 will be displayed.

---

**Question 2:**

Write an SQL query to fetch the IDs and names of employees who completed more than 5 projects in the last year.

**Answer:**

```sql
SELECT e.employee_ID, e.name
FROM employee_information e
JOIN project_assignments p
ON e.employee_ID = p.employee_ID
WHERE p.year = '2023' AND p.project_count > 5;
```

**Explanation:**

- **`SELECT e.employee_ID, e.name`:** Specifies that we need the employee ID and name.
- **`FROM employee_information e`:** Fetches data from the `employee_information` table.
- **`JOIN project_assignments p ON e.employee_ID = p.employee_ID`:** Joins the `employee_information` table with the `project_assignments` table using the common column `employee_ID`.
- **`WHERE p.year = '2023' AND p.project_count > 5`:** Filters the results to include employees who completed more than 5 projects in 2023.

**Result:**

- A list of employee IDs and names who completed more than 5 projects in the last year will be displayed.

---

**Tips for Understanding the Solutions:**

- Focus on the relationships between tables by identifying common columns like `product_ID` or `employee_ID`.
- Use filtering conditions in the `WHERE` clause to narrow down results to meet the criteria.
- Aggregate or compute values where necessary (e.g., `SUM`, `COUNT`, or arithmetic operations).

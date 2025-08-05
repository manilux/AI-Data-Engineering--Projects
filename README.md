# AI-Data-Engineering--Projects
My Journey Mastering SQL, Py Spark, Databricks &amp; Snowflake For AI Data Engineering

WITH ranked_salaries AS (
  SELECT *,
    ROW_NUMBER() OVER (PARTITION BY dept_id ORDER BY salary DESC) AS rnk
  FROM employees
)
SELECT *
FROM ranked_salaries
WHERE rnk = 2;

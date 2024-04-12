# pyspark_projects
A project series to learn and apply pyspark functionalities

### Project 1:
-------------------------
- Common Spark understanding:
  ---
  - In the expression sum('price'), 'price' is being interpreted as a column name, and the sum function is attempting to sum the values in that column. However, if the values in the 
    'price' column are strings instead of numeric types (e.g., integers or floats), then attempting to sum them will result in the error TypeError: unsupported operand type(s) for +: 
    'int' and 'str', because you cannot perform addition on a mix of numeric and string values.
  - On the other hand, when you use agg({"price": "sum"}), you are explicitly specifying the aggregation operation to be performed on the 'price' column using a dictionary syntax. This 
    tells Spark to use the sum function to aggregate the values in the 'price' column. Spark's sum function is designed to handle numeric values, so it will internally handle the 
    conversion of string representations of numbers to actual numeric types before performing the summation.

  - In summary, using agg({"price": "sum"}) provides more explicit control over how the aggregation is performed and allows Spark to handle any necessary type conversions internally.
    In short even if we don't change the schema of a string column to intger it will still sum them with the help of agg({"price": "sum"})

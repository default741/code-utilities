# Utility Function Snippets

This repository contains a collection of reusable Python code snippets and utility functions organized as Jupyter notebooks. These are designed to accelerate development and experimentation across a range of tasks including data processing, logic circuit generation, quantum circuit analysis, and more. Each notebook is self-contained, well-documented, and ready to integrate into larger projects or use for quick prototyping.

## Notebooks

### Logic Circuits Functions

 - `create_truth_table`: Generate and optionally print the truth table for a custom Boolean operation.

```python
# Example usage: generate and print the truth table for the custom operation
inputs, outputs = create_truth_table(num_inputs=4,
                                     operation=custom_operation,
                                     print_table=True)

# Output
# | I0 | I1 | I2 | I3 | OP |
# --------------------------
# |  0 |  0 |  0 |  0 |  0 |
# |  0 |  0 |  0 |  1 |  1 |
# |  0 |  0 |  1 |  0 |  1 |
# |  0 |  0 |  1 |  1 |  1 |
# |  0 |  1 |  0 |  0 |  1 |
# |  0 |  1 |  0 |  1 |  0 |
# |  0 |  1 |  1 |  0 |  1 |
# |  0 |  1 |  1 |  1 |  1 |
# |  1 |  0 |  0 |  0 |  1 |
# |  1 |  0 |  0 |  1 |  1 |
# |  1 |  0 |  1 |  0 |  0 |
# |  1 |  0 |  1 |  1 |  1 |
# |  1 |  1 |  0 |  0 |  1 |
# |  1 |  1 |  0 |  1 |  1 |
# |  1 |  1 |  1 |  0 |  1 |
# |  1 |  1 |  1 |  1 |  0 |
# --------------------------
```

 - `custom_operation`: Custom Boolean operation: returns 0 if the first half of the input bits matches the second half; otherwise returns 1.
 - `generate_circuit_expression`: Generate a Boolean circuit expression (CNF-style) based on the given truth table.

```python
# Generate a Boolean circuit expression (CNF-style) based on the given truth table.
generate_circuit_expression(inputs=inputs, outputs=outputs)

# Output
# '(c0 OR c1 OR c2 OR c3) AND (c0 OR NOT(c1) OR c2 OR NOT(c3)) AND (NOT(c0) OR c1 OR NOT(c2) OR c3) AND (NOT(c0) OR NOT(c1) OR NOT(c2) OR NOT(c3))'
```
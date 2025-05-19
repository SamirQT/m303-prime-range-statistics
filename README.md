## M303: Prime Range & Statistics Analysis

**Assignment Overview:**
In this project, you will implement two Python functions to identify and analyze prime numbers within a given integer range—using only primitive types, loops, and conditionals (no lists or dictionaries). Your functions will:

1. **`is_prime(n)`**: Determine whether a single integer `n` is prime, returning both a boolean result and, when composite, its smallest divisor.
2. **`analyze_primes(a, b)`**: Iterate from `a` to `b` (inclusive), use `is_prime` to collect every prime into a space-separated string, count them, and sum them.

This assignment reinforces control-flow logic, loop design, and function composition.

---

**Objectives:**
By completing this assignment, you will:

* Write a primality test that checks divisors only up to √n.
* Build a loop to scan a numeric range without extra data structures.
* Aggregate string, count, and sum outputs in a single pass.
* Handle invalid input ranges gracefully within your function.
* Encapsulate each piece of logic in its own reusable function.

> **Note:** Do **not** use lists, dictionaries, or helper methods like `.split()`—only loops, integer arithmetic, and basic strings.

---

**Instructions:**

1. **`is_prime(n)` Function**

   * Signature:

     ```python
     def is_prime(n):
         """
         Checks whether integer n is prime.
         Returns:
           (True, None)          if n is prime (n > 1),
           (False, divisor)      if n is composite,
           (False, None)         if n <= 1.
         """
         # your implementation
     ```
   * Logic:

     * If `n <= 1`, it’s not prime.
     * Otherwise, test `d` from 2 up to `int(n**0.5)`:

       * If `n % d == 0`, return `(False, d)`.
     * If no divisors found, return `(True, None)`.

2. **`analyze_primes(a, b)` Function**

   * Signature:

     ```python
     def analyze_primes(a, b):
         """
         Analyzes primes in the inclusive range [a, b].
         Returns:
           primes_str (str)   — primes joined by spaces ("" if none),
           count      (int)   — number of primes found,
           total      (int)   — sum of those primes.
         If a >= b or b <= 1, returns ("", 0, 0).
         """
         # your implementation
     ```
   * Logic:

     * If `a >= b` or `b <= 1`, return empty results.
     * Loop `n` from `a` to `b`:

       * Call `is_prime(n)`.
       * If prime, append `str(n) + " "` to `primes_str`, increment `count`, add to `total`.
     * After the loop, trim trailing space from `primes_str` if any primes found.

---

**Technical Requirements:**

* **Data Types:** Only integers and strings.
* **Loops:** Use `for` or `while` loops.
* **Conditionals:** Use `if`/`else` for range checks and divisor tests.
* **Functions:** Two functions—`is_prime` and `analyze_primes`.
* **No Extra Structures:** Avoid lists, dictionaries, and built-in splitting or collection methods.

---

**Deliverables:**

* **Python Script:**

  * File name: `M303_prime_stats.py`
  * Contains **only** the two function definitions as specified (no `main` or I/O code).

---

**Example of Usage:**

```python
primes_str, count, total = analyze_primes(10, 30)
# primes_str == "11 13 17 19 23 29"
# count      == 6
# total      == 112

# For invalid range:
primes_str, count, total = analyze_primes(20, 5)
# primes_str == ""
# count      == 0
# total      == 0
```

---

**Evaluation Criteria:**

* **Correctness (50%)**

  * Accurate primality test up to √n.
  * Proper range scanning and aggregation.
* **Code Quality (30%)**

  * Clear, well-commented functions with meaningful variable names.
* **Edge-Case Handling (20%)**

  * Graceful handling of invalid or degenerate ranges.

---

**Tip for Success:**
Sketch your divisor-check loop on paper first—identify exactly when to exit early on finding a divisor. Then build your range loop around this helper function to collect and summarize primes efficiently.


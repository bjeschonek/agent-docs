---
trigger: model_decision
description: Apply this rule during data structure design, collection processing, or performance-sensitive logic implementation to ensure optimal time complexity.
---

# Rule: Algorithmic Complexity Gate
## 1. Target Efficiency
* All core data collection lookups, insertions, and updates must execute with **O(1)** or **O(log n)** time complexity. 

## 2. Prohibited Patterns
* Nested loops creating **O(n²)** or worse operations on dynamically sized collections are strictly banned unless alternatives are mathematically impossible.
* Avoid native sequential array lookups (`.find()`, `.includes()`) in hot paths.

## 3. Preferred Primitives
* Default to **Maps**, **Sets**, or pre-allocated flat arrays over standard array searching.

## 4. Enforcement & Justification
* If a solution requires **O(n²)** complexity, you must insert an explicit `// PERFORMANCE JUSTIFICATION:` comment detailing the structural bottleneck and why a hash map or balanced tree was bypassed and why a more efficient structure (like a Hash Map or Balanced Tree) was not used.
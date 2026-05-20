---
trigger: model_decision
description: Apply this rule when working with high-frequency loops, hot paths, or large data streams to prevent memory leaks and garbage collection (GC) pressure.
---

# Rule: Memory Hygiene & GC Spike Prevention
## 1. Allocation Cap
* Zero unnecessary intermediate heap allocations within hot paths, loops, or frequently executed event listeners.

## 2. Array Chaining & Transformation
* Avoid intermediate array generation via chained functional operations (e.g., executing `.map().filter().reduce()` sequentially). 
* Rewrite as a single `.reduce()` or a localized, high-performance `for` loop to minimize short-lived objects.

## 3. Object Reuse
* Favor mutating existing objects or structures in place inside closed computational loops rather than instantiating short-lived objects or closures.

## 4. Local Mutability Exception
* Local mutable variables are mandatory within micro-scopes if they actively prevent heap allocation spikes or optimize garbage collection overhead. Standard immutability rules are suspended for local performance optimization.
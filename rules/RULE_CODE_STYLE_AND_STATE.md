---
trigger: model_decision
description: Apply this rule when creating new modules, refactoring code, or designing data transformation pipelines to ensure strict modularity, readability, and predictable state management.
---

# Rule: Code Cleanliness, Modularity, and State Constraints 

## 1. Modularity & File Scale
* **Maximize Modularity:** Core functionality must be completely isolated into specialized, single-responsibility utility modules.
* **Avoid File Bloat:** If a module exceeds **200 lines of code**, you must immediately extract its sub-functions into independent files.

## 2. Declarative Pipelines & Immutability First
* **Immutability First:** Treat all incoming data structures as strictly read-only. Transform data by returning fresh structures rather than modifying existing arguments in place.
* **Prefer Functional Primitives:** Utilize high-order array operations (`map`, `filter`, `reduce`) over imperative loops to maximize readability and maintain pure, side-effect-free code.

## 3. Memory Optimization Exception
* **Restricted In-Place Mutation:** In-place mutations are strictly banned *except* inside low-level, performance-critical data structures (e.g., pre-allocated circular buffers or custom linked lists) where memory reuse is structurally vital. 
* **Documentation:** You must document these specific blocks with explicit inline complexity and memory hygiene justifications.
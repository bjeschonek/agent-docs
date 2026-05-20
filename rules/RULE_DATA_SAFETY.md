---
trigger: model_decision
description: Apply this rule at the entry points of utilities, API routes, or mathematical routines to safeguard against numeric overflow, invalid input types, and unhandled exceptions.
---

# Rule: Data Boundary and Precision Safeguards

## 1. Arbitrary Precision Math
* **Type Boundary Verification:** Always verify numerical type boundaries before processing.
* **Large Int Handling:** If a routine performs mathematical evaluation, high-frequency tracking, or counts beyond standard integer limits, utilize arbitrary-precision types (such as native `BigInt` or specialized math libraries) by default.

## 2. Strict Input Sanitization
* **Structural Validation:** Every single entry point to a utility, module, or public function must validate the shape, type, and presence of its inputs before executing any core logic.

## 3. Error Containment & Isolation
* **Zero Naked Bubbling:** Never allow raw errors to bubble up unhandled across system layers. 
* **Localized Boundary Checks:** Wrap complex or volatile operations in distinct, localized boundary checks that catch exceptions and fail gracefully by returning highly descriptive, explicitly typed error interfaces.
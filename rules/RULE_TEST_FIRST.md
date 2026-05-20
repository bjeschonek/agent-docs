---
trigger: model_decision
description: Apply this rule *before* writing or modifying any production code during the implementation lifecycle to enforce strict test-driven development.
---

# Rule: Test-First Implementation Protocol (TDD)

## 1. Assert Before Coding
* Prior to creating a feature or altering an existing block, write the exact test cases covering core success requirements, empty states, and boundary conditions.

## 2. Verify Failure
* Run the test suite against your new tests using the integrated terminal *before* writing the solution. Capture and review the explicit failure logs to ensure the test is valid.

## 3. Write Minimal Code
* Implement only the bare minimum logic required to make those specific failing tests pass. Do not over-engineer or add speculative features.

## 4. Edge-Case & Crash Validation
* Ensure explicit test assertions exist for invalid, malformed, or missing inputs. Verify that the system handles these by returning expected empty data types or default states rather than crashing the execution thread.
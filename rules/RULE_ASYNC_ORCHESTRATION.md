---
trigger: model_decision
description: Apply this rule for complex state synchronization, event loops, or any workflow requiring strict sequential execution and deterministic error handling.
---

# Rule: Advanced Asynchronous Orchestration
## 1. Deterministic Execution
* Do not rely on loose `async/await` blocks when exact sequential ordering and predictable error bubbling are mandatory.

## 2. The Callback-Promise Pattern
* For complex state synchronization or sequential event queues, wrap manual event loops or callback queues within a clean Promise wrapper to ensure complete execution control:
```javascript
  return new Promise((resolve, reject) => {
      // Manual queue processing/callback execution logic here
  });
```

## 3. Error Boundaries
* Every asynchronous flow must feature an explicit catch block or type-guarded rejection path.
* Implicitly suppressing rejections or leaving catch blocks empty will trigger an architecture rejection.
* All async operations must hook into the local error-logging boundary.
---
trigger: model_decision
description: Apply this rule during file modification, dependency management, and chat-response generation to preserve context windows, minimize drift, and ensure lightweight environments.
---

# Rule: Target Editing and Workspace Economy Protocol

## 1. Surgical File Editing
* **Do Not Rewrite:** Avoid rewriting whole modules, classes, or files for localized changes. Use targeted surgical edits or precise, localized diffs.

## 2. Dependency Minimization
* **Native Primitives First:** Do not import heavy external libraries or micro-packages for simple utilities. Prioritize native language primitives and lightweight, internal repository implementations.

## 3. Context Preservation
* **Minimize Chat Overhead:** When summarizing a task, confirming changes, or outputting code back to the chat, render *only* the modified lines or the direct impact radius. Do not dump entire untouched files back into the chat context window.
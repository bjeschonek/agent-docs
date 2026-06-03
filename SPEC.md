# SPEC.md — [Project or Feature Name] Specification

* **Status:** [Draft / Under Review / Approved / Implemented]
* **Author(s):** [Your Name / Team]
* **Last Updated:** [YYYY-MM-DD]
* **Tracking Issue/Ticket:** [e.g., Jira-101 / GitHub #42]

---

## 1. Executive Summary & Goals

### High-Level Problem
[A brief 2-3 sentence description of the user problem or business need. Why are we building this?]

### Objectives (In-Scope)
* [Clear, measurable goal 1]
* [Clear, measurable goal 2]

### Non-Goals (Out-of-Scope)
* [Explicitly state what this feature/project will NOT do to prevent scope creep.]
* [Out-of-scope item 2]

---

## 2. User Experience & Flows

### Target Persona
[Describe the user, e.g., "Active day traders who need real-time data adjustments without UI lag."]

### Core User Journey
1. **Entry:** The user navigates to `...`
2. **Action:** The user triggers `...`
3. **Outcome:** The system updates `...`

---

## 3. Technical Architecture & Design

### System Overview
[Briefly explain how components interact. If applicable, mention the specific architectural patterns used, such as functional pipelines, event-driven state, or static-dynamic hybrids.]

### Data Model & Schema
Define the primary structures or database schemas here. Use strict types or interfaces.

```typescript
interface CoreEntity {
  id: string;
  createdAt: number; // Unix timestamp
  status: 'pending' | 'active' | 'archived';
  // Add additional strict fields here
}
```

### Component Breakdown
* **Frontend/UI:** [e.g., Declarative, stateless components; specific layout structures; Tailwind design constraints]
* **Backend/API:** [e.g., REST endpoints, Fastify routes, or WebSockets details]
* **State Management:** [e.g., Immutable local state, client-side caching strategies]

## 4. API & Interface Contracts
### **Endpoint:** [METHOD] /api/v1/resource
* **Description:** [What it does]
* **Authentication:** [Yes / No / Role Required]

### Request Payload

```json
{
  "key": "value"
}
```
### Response Payload (Success 200 OK)

```json
{
  "success": true,
  "data": {}
}
```

### Error States
* 400 Bad Request: If [parameter] is missing or malformed.
* 404 Not Found: If the resource ID does not exist.

## 5. Performance, Constraints & Edge Cases
### Algorithmic & Performance Targets
* **Time/Space Complexity:** Critical paths must operate at optimal efficiency (target $O(1)$ or $O(\log n)$ where possible). Avoid heavy nesting or redundant lookups.
* **Network & Latency:** [e.g., UI components must render immediately using stale-while-revalidate (SWR) or local caching to prevent layout shifts.]

### Critical Edge Cases to Handle
* **Network Failure/Offline Mode:** How does the system degrade gracefully?
* **Empty/Null States:** What happens when data arrays return empty?
* **Mathematical / Boundary Limits:** Extreme values, division by zero, or invalid status combinations must throw explicit, readable errors rather than failing silently.

## 6. Implementation Phases & Milestones
* [ ] Phase 1: Foundations — Core schemas, database migrations, and basic backend API routes.
* [ ] Phase 2: Core Logic — Implementation of functional data processing and state management algorithms.
* [ ] Phase 3: UI & Integration — Connecting declarative frontend components to the backend API.
* [ ] Phase 4: Verification — Unit tests covering edge cases, integration tests, and performance profiling.

---

### Why this structure works:
* **Scope Isolation:** The **Non-Goals** section is critical. It acts as an immediate stopping block for both human developers and LLMs who might otherwise write unrequested code.
* **Strict Data Contracts:** Providing explicit TypeScript interfaces or JSON blocks ensures that when an AI parses the document, it builds integration layers with exact structural alignment.
* **Edge-Case Blueprinting:** Forcing the consideration of empty states, math errors, and performance limits at the spec level results in defensive, production-ready code right from the first commit.

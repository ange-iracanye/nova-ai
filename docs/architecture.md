> **Historical prototype documentation:** This describes an earlier Nova design, not a verified map of the current application. For the canonical codebase, current architecture, setup, and release status, see [ange-iracanye/Nova](https://github.com/ange-iracanye/Nova).

# Nova Architecture

Nova's early design explored a modular AI tutoring system that separates student context, memory, knowledge retrieval, tutoring logic, prompt construction, and model inference.

The sections below preserve the original architectural concepts for reference. They should not be used as evidence that every component is present or active in the current application.

---

## High-Level Architecture

```text
Student
   ↓
Conversation and intent detection
   ↓
Student context + memory + knowledge retrieval
   ↓
Tutor engine and prompt construction
   ↓
Language model
   ↓
Response and possible learning update
```

## Design goals

- Route different student requests through appropriate tutoring behavior.
- Use relevant student context rather than treating every request as isolated.
- Retrieve knowledge when it can improve an answer.
- Keep tutoring logic distinct from model-specific inference.
- Evaluate personalization and retrieval instead of assuming that a component works because it exists.

For implementation details, run the tests and inspect the current source in the canonical repository.
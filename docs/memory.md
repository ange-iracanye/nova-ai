> **Historical prototype documentation:** These notes describe the earlier Nova memory design and are not a guarantee of current production behavior. See the [canonical Nova repository](https://github.com/ange-iracanye/Nova) for current code and release checks.

# Nova Memory System

The early design explored memory as a way to preserve useful context between tutoring conversations. The goal was not to remember everything, but to retain information that could improve future learning.

## Intended flow

```text
Conversation
    ↓
Candidate information extraction
    ↓
Validation and metadata
    ↓
Storage and retrieval
    ↓
Relevant student context
    ↓
Personalized tutoring
```

## Metadata considered

The prototype documentation considered fields such as:

```text
type
text
subject
conversation_id
importance
confidence
```

These are design notes, not a claim that all fields are reliably extracted or persisted in the current application.

## Quality questions

A useful memory system should be evaluated for:

- **Relevance:** does this help future tutoring?
- **Accuracy:** was the information extracted correctly?
- **Confidence:** how reliable is the extracted fact?
- **Importance:** is the information worth retaining?
- **Persistence:** should it remain available in later sessions?
- **Privacy:** should the information be stored at all, and how can it be corrected or deleted?

Natural-language extraction can be imperfect. Current behavior must be verified against the canonical repository and its tests.

## Design principle

> Remember information when it helps the student learn, and handle student data deliberately.
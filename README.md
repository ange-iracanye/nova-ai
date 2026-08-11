# Nova AI 

> **An adaptive AI tutoring system designed to help students understand, learn, and improve.**

Nova is a personal AI tutoring project focused on a simple idea:

> **An AI tutor should understand the student, not just the question.**

Instead of treating every conversation as an isolated request, Nova is being designed around **student context, memory, knowledge retrieval, adaptive tutoring, and personalized learning**.

Nova is my main long-term AI and software engineering project.

---

## Why Nova?

General-purpose AI assistants are good at answering questions.

Nova is being built around a different problem:

**How can an AI system actually behave like a useful personal tutor?**

That means considering things such as:

* What does the student already know?
* What are they currently studying?
* What have they struggled with before?
* How confident are they?
* Which explanation strategy should be used?
* What information should be remembered?
* Which knowledge should be retrieved?
* When should a tool be used instead of the language model?

Nova is an attempt to engineer systems around these questions.

---

# Current Features

Nova is under active development.

### AI & Tutoring

* [x] Local LLM inference
* [x] Tutor Engine
* [x] Prompt construction
* [x] Student-aware tutoring context
* [x] Adaptive tutoring architecture
* [ ] Advanced tutoring evaluation

### Memory

* [x] Conversation context
* [x] Memory extraction
* [x] Memory metadata
* [x] Student-related memory
* [x] Confidence tracking
* [ ] More reliable structured fact extraction
* [ ] Advanced long-term memory retrieval

### Knowledge

* [x] Knowledge loading
* [x] Knowledge retrieval
* [x] Embedding-based search
* [x] Relevance thresholding
* [ ] Larger knowledge system
* [ ] Automated retrieval evaluation

### Student System

* [x] Student profile
* [x] Subject context
* [x] Understanding/confidence tracking
* [x] Learning context
* [ ] More advanced learning analytics

### Tools & Intelligence

* [x] Intent detection
* [x] Skill system
* [x] Calculator support
* [x] Internet-related tooling
* [ ] More advanced tool selection

### Application

* [x] Web interface
* [x] Chat interface
* [x] Dashboard
* [x] Study system
* [x] Quiz system
* [x] Upload functionality
* [x] Settings
* [x] Code rendering

---

# Architecture

Nova is designed as a modular AI system.

A simplified representation of the current architecture is:

```text
                         ┌─────────────────┐
                         │     Student     │
                         └────────┬────────┘
                                  │
                                  ▼
                         ┌─────────────────┐
                         │ Intent Detector │
                         └────────┬────────┘
                                  │
                 ┌────────────────┼────────────────┐
                 │                │                │
                 ▼                ▼                ▼
          ┌────────────┐   ┌────────────┐   ┌────────────┐
          │   Memory   │   │ Knowledge  │   │   Tools    │
          │   System   │   │  Retrieval │   │ Calculator │
          └──────┬─────┘   └──────┬─────┘   └──────┬─────┘
                 │                │                │
                 └────────────────┼────────────────┘
                                  │
                                  ▼
                         ┌─────────────────┐
                         │   TutorEngine   │
                         └────────┬────────┘
                                  │
                                  ▼
                         ┌─────────────────┐
                         │  PromptBuilder  │
                         └────────┬────────┘
                                  │
                                  ▼
                         ┌─────────────────┐
                         │    Local LLM    │
                         └────────┬────────┘
                                  │
                                  ▼
                              Response
                                  │
                                  ▼
                         Memory / Learning
                              Update
```

The architecture is intentionally modular so individual systems can be improved without rewriting the entire application.

---

# Core Systems

## TutorEngine

The TutorEngine coordinates Nova's tutoring process.

It brings together information such as:

* student context
* subject
* current question
* tutoring mode
* tutoring strategy
* understanding/confidence

and passes the relevant context toward prompt construction and model generation.

---

## PromptBuilder

`PromptBuilder` separates prompt construction from the TutorEngine.

The basic flow is:

```text
Student Context
      ↓
Subject
      ↓
Question
      ↓
Mode
      ↓
Strategy
      ↓
PromptBuilder
      ↓
System + User Prompt
      ↓
Local LLM
```

This separation makes the tutoring architecture easier to modify and experiment with.

---

## Memory System

Nova includes a memory system designed to extract useful information from conversations.

Memory can contain information such as:

```text
type
text
subject
conversation
importance
confidence
```

The system is being developed toward long-term student personalization.

One current development area is improving the reliability of natural-language fact extraction.

For example, a statement such as:

```text
"My name is Michael."
```

should ideally become a structured fact rather than simply storing an incomplete piece of text.

---

## Knowledge Retrieval

Nova uses a retrieval system to find relevant information before generating certain responses.

The system includes:

* knowledge loading
* embeddings
* similarity search
* relevance filtering

This allows Nova to combine retrieved information with the student's context before generating an answer.

---

## Student Profile

Nova maintains a student-oriented context containing information useful for tutoring.

The system can work with information such as:

* learning history
* subjects
* questions
* answers
* understanding
* confidence

The long-term goal is for this information to influence how Nova teaches.

---

## Adaptive Tutoring

Nova is being developed around adaptive tutoring rather than simply question answering.

The intended process is:

```text
Student Question
      ↓
Understand Context
      ↓
Determine Student State
      ↓
Choose Teaching Strategy
      ↓
Generate Explanation
      ↓
Evaluate Understanding
      ↓
Update Student Context
```

This system is still being actively improved.

---

# Local AI

Nova uses local language models rather than depending entirely on an external AI API.

The local inference system is designed to:

1. Load the model
2. Process the prompt
3. Generate new tokens
4. Decode only the generated response
5. Return the result to the tutoring system

Keeping the model layer separate from the tutoring architecture allows Nova's AI backend to evolve independently.

---

# Technology Stack

### Backend

* Python
* Flask

### AI

* Local language models
* Transformers
* Embeddings
* Retrieval systems

### Frontend

* JavaScript
* React
* HTML/CSS
* Tailwind CSS

### Architecture

* Modular Python components
* REST APIs
* JSON-based persistence
* Git/GitHub

---

# Project Structure

The project is being organized around separate responsibilities.

A simplified structure is:

```text
nova-ai/
│
├── backend/
│   ├── tutor_engine/
│   ├── memory_system/
│   ├── knowledge/
│   ├── llm/
│   ├── profile/
│   ├── tools/
│   └── ...
│
├── frontend/
│
├── tests/
│
├── docs/
│
├── requirements.txt
├── .gitignore
└── README.md
```

The exact structure may evolve as the architecture develops.

---

# Running Nova

Nova is currently a development project.

## Requirements

* Python
* Git
* Required Python dependencies
* A compatible local AI model

## Installation

Clone the repository:

```bash
git clone https://github.com/ange-iracanye/nova-ai.git
cd nova-ai
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Then start Nova using the project's application entry point.

> The exact startup command may change while the project is under active development.

---

# Testing

Nova is being developed with testing in mind.

The test suite is being expanded around important systems such as:

* Memory extraction
* Knowledge retrieval
* Prompt construction
* TutorEngine
* Tool selection
* Student context

Testing is particularly important for Nova because many of its systems depend on interpreting natural-language input.

---

# Roadmap

## Current

* [x] Local AI inference
* [x] Tutor Engine
* [x] PromptBuilder
* [x] Student profile
* [x] Conversation memory
* [x] Memory extraction
* [x] Knowledge retrieval
* [x] Embedding search
* [x] Intent detection
* [x] Tool system
* [x] Quiz system
* [x] Web interface

## In Development

* [ ] Improve memory extraction accuracy
* [ ] Improve long-term memory retrieval
* [ ] Improve adaptive tutoring strategies
* [ ] Add automated tests
* [ ] Evaluate retrieval quality
* [ ] Improve student understanding tracking
* [ ] Improve tutoring decisions
* [ ] Improve model response quality

## Future

* [ ] Advanced learning analytics
* [ ] More sophisticated study planning
* [ ] Stronger mathematical reasoning
* [ ] Improved coding assistance
* [ ] More advanced personalization
* [ ] Larger knowledge systems
* [ ] User feedback system
* [ ] Public deployment
* [ ] Performance optimization

---

# Known Limitations

Nova is still an experimental project.

Some systems are functional but still being improved.

In particular:

* Memory extraction can produce imperfect facts.
* Retrieval quality needs more systematic evaluation.
* Adaptive tutoring is still being refined.
* The local model's capabilities depend heavily on the selected model.
* The project has not yet been optimized for production-scale deployment.

These limitations are part of the development process and are being addressed through testing and iteration.

---

# Why I Built Nova

Nova started as a personal project to explore how artificial intelligence could make learning more personalized.

It has since become a larger exploration of:

* AI engineering
* Software architecture
* Natural language processing
* Retrieval systems
* Local language models
* Educational technology
* Personalization
* Full-stack development

The project is also my main way of learning how complete AI systems are designed, implemented, tested, and improved.

---

# Vision

The long-term goal is simple:

> **Build an AI tutor that students genuinely prefer to use for learning.**

Nova is not intended to become another general-purpose chatbot.

Its focus is **education and personalized learning**.

The project will continue evolving as I learn more about artificial intelligence, mathematics, computer science, and software engineering.

---

# Author

**Ange Iracanye**

Terminale student and aspiring AI engineer.

Nova is an independent long-term project focused on learning through building.

---

## License

This project is currently under active development.

## What do I need to do to use **ERIC.AI**?
ERIC.AI uses a combination of documentation and historical question and Test case  pairs to generate TOL from natural language.

### Step 1: Train **Eric.AI**
- Give **ERIC.AI** sample TOL
- **ERIC.AI** will try to guess the question
- Verify the question is correct
```mermaid
flowchart LR
    Generate[E.generate_question]
    Question[Question]
    Verify{Is the question correct?}
    TOL --> Generate
    Generate --> Question
    Question --> Verify
    Verify -- Yes --> Store[E.store_sql]
    Verify -- No --> Update[Update the Question]
    Update --> Store
    
```

### Step 2: Ask **ERIC.AI** a Question
```mermaid
flowchart LR
    Question[Question]
    Generate[E.generate_TOL]
    TOL[TOL]
    Question --> Generate
    Generate --> TOL    
```

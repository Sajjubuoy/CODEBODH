# CodeBodh – AI Tutor for Concept Gap Resolution

![Architecture](docs/architecture.png)

## Overview

**CodeBodh** is an AI-powered tutoring system designed to help programming students understand **conceptual mistakes in their code** instead of only showing raw error messages.

Traditional compilers and interpreters return technical errors that beginners often struggle to understand. CodeBodh analyzes student code, detects errors, maps them to programming concepts, and provides **guided conceptual explanations and hints**.

The system combines **program analysis techniques and Large Language Models** to create a **concept-driven learning assistant**.

---

## System Architecture

The architecture consists of four primary layers:

1. Input and Interface
2. Code Analysis
3. Pedagogy and AI
4. Output and Student Feedback

---

## 1. Input and Interface

Students interact with the system through a simple user interface.

### Components

* **Student Code Input**
* **Gradio Interface**

The student submits their code through the interface, which forwards the code to the backend analysis system.

---

## 2. Code Analysis

This layer performs program inspection and detects errors in the submitted code.

### Program Analyzer

The program analyzer performs:

* Abstract Syntax Tree (AST) analysis
* Runtime execution
* Structural code inspection

This helps identify issues such as:

* Undefined variables
* Logical mistakes
* Syntax errors
* Incorrect use of programming constructs

### Error Detection

The system captures:

* Python exceptions
* Traceback details
* Error messages
* Faulty code location

These detected errors are passed to the pedagogical layer.

---

## 3. Pedagogy and AI Layer

This layer converts programming errors into **learning opportunities**.

### Error to Concept Mapper

This module maps detected errors to the **underlying programming concepts**.

Example mappings:

| Error Type     | Concept                     |
| -------------- | --------------------------- |
| NameError      | Variables                   |
| TypeError      | Data Types                  |
| IndexError     | Lists / Arrays              |
| AttributeError | Object-Oriented Programming |

This step transforms low-level technical errors into **educational insights**.

---

### Pedagogical Prompt Builder

This module constructs a structured prompt for the LLM including:

* Student code
* Detected error
* Related programming concept
* Instructions to generate conceptual explanations and hints

The goal is to guide the model to provide **teaching-style explanations** instead of direct solutions.

---

### Mistral 7B LLM

CodeBodh uses:

**Mistral 7B Instruction Model (4-bit Quantized)**

The model generates:

* Concept explanations
* Reasoning behind the error
* Step-by-step hints
* Learning guidance

This makes the system behave like an **AI programming tutor**.

---

## 4. Output Layer

### Concept-Based Feedback

Instead of simply returning an error message, the system generates:

* Explanation of the concept
* Why the error occurred
* Hints to fix the mistake
* Suggestions for learning

### Student Interface

The explanation is displayed through the UI so students can clearly understand their mistake and improve their programming knowledge.

---

## Example Pipeline Flow

```
Student Code
     ↓
Gradio Interface
     ↓
Program Analyzer (AST + Runtime)
     ↓
Error Detection
     ↓
Error → Concept Mapping
     ↓
Pedagogical Prompt Builder
     ↓
Mistral 7B LLM
     ↓
Concept-Based Feedback
     ↓
Student Explanation Interface
```

---

## Tech Stack

### Programming

* Python

### Machine Learning

* PyTorch
* Transformers
* Mistral 7B

### Interface

* Gradio
* Streamlit

### Code Analysis

* Python AST
* Runtime Execution
* Error Traceback

### Deployment

* Docker
* Google Colab

---

## Project Structure

```
CodeBodh
│
├── app
│   └── streamlit_app.py
│
├── codebodh
│   ├── diagnostic.py
│   ├── concept_mapper.py
│   ├── prompt_builder.py
│   └── llm_engine.py
│
├── notebooks
│   └── training_pipeline.ipynb
│
├── docs
│   └── architecture.png
│
├── Dockerfile
├── requirements.txt
└── README.md
```

---

## Future Improvements

* Multi-language support (C++, Java, Python)
* Graph-based knowledge retrieval
* Personalized tutoring feedback
* Concept difficulty estimation
* Student learning analytics

---

## Author

**Mahammad Sajjad**
BTech – Artificial Intelligence & Machine Learning
Alliance University, Bangalore

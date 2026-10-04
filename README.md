# Test the Code Reviewer with Different Code Defects

## 📌 Project Overview

This project evaluates the effectiveness of an **LLM-Based Code Review Assistant** by testing it on Python code containing multiple software defects.

The objective is to determine whether the code-review assistant can successfully identify, explain, and recommend fixes for various types of issues, including security vulnerabilities, code-quality problems, style violations, and potential runtime errors.

The project combines static-analysis tools and an LLM to generate a comprehensive code-review report.

---

## 🎯 Objectives

The main objectives of this project are:

* Test a code-review assistant using defective source code.
* Detect security vulnerabilities in Python programs.
* Identify code-quality issues.
* Find style and formatting violations.
* Detect potential runtime problems.
* Generate automated review reports.
* Explain identified defects.
* Recommend appropriate fixes and improvements.

---

## 🛠️ Technologies Used

| Technology   | Purpose                               |
| ------------ | ------------------------------------- |
| Python       | Source code development               |
| Flake8       | Style and lint analysis               |
| Pylint       | Code quality analysis                 |
| Bandit       | Security vulnerability detection      |
| LLM          | Issue explanation and recommendations |
| Google Colab | Development environment               |
| GitHub       | Version control and project hosting   |

---

## 📂 Project Structure

```text
Test-Code-Reviewer-With-Different-Code-Defects/
│
├── test_defects.py
├── README.md
│
├── flake8_report.txt
├── pylint_report.txt
├── bandit_report.txt
│
└── review_report.txt
```

---

## 🔍 Sample Source Code

The project analyzes the following Python file:

```python
import os
import subprocess

password = "admin123"

def divide(a,b):
    return a/b

def execute_command(cmd):
    os.system(cmd)

unused_variable = 100

# Reviewer should detect this issue without crashing execution
print("Potential issue: divide(10, 0)")
```

---

## 📋 Defects Included

### 1. Hardcoded Password

```python
password = "admin123"
```

**Issue:** Sensitive credentials are stored directly in source code.

**Risk:** Security vulnerability.

---

### 2. Unused Import

```python
import subprocess
```

**Issue:** Imported module is never used.

**Risk:** Reduces code clarity and maintainability.

---

### 3. Formatting Issue

```python
def divide(a,b):
```

**Issue:** Missing whitespace after comma.

**Risk:** Violates PEP 8 coding standards.

---

### 4. Unsafe Command Execution

```python
os.system(cmd)
```

**Issue:** May allow command injection attacks.

**Risk:** Security vulnerability.

---

### 5. Unused Variable

```python
unused_variable = 100
```

**Issue:** Variable is declared but never used.

**Risk:** Unnecessary code complexity.

---

### 6. Missing Documentation

**Issue:** Functions do not contain docstrings.

**Risk:** Reduced readability and maintainability.

---

### 7. Potential Runtime Error

```python
divide(10, 0)
```

**Issue:** Division by zero may occur.

**Risk:** Runtime failure if executed.

---

## 🔎 Static Analysis Process

The project uses the following tools:

```bash
pip install flake8 pylint bandit
```

Generate reports:

```bash
flake8 test_defects.py > flake8_report.txt

pylint test_defects.py > pylint_report.txt

bandit -r test_defects.py > bandit_report.txt
```

---

## 🤖 LLM Review Process

The generated reports are combined and provided to the LLM.

The LLM performs:

1. Issue identification
2. Issue explanation
3. Risk assessment
4. Fix recommendation
5. Review report generation

---

## ✅ Expected Findings

The code-review assistant should identify:

* Hardcoded password
* Unused import
* Formatting issues
* Unsafe use of `os.system()`
* Unused variable
* Missing documentation
* Potential division-by-zero error

---

## 🔄 Workflow

```text
        Defective Python Code
                  ↓
        ┌─────────────────┐
        │     Flake8      │
        ├─────────────────┤
        │     Pylint      │
        ├─────────────────┤
        │     Bandit      │
        └─────────────────┘
                  ↓
          Analysis Reports
                  ↓
           Combined Report
                  ↓
              LLM Prompt
                  ↓
           LLM Code Review
                  ↓
        Defect Explanations
                  ↓
        Suggested Fixes
                  ↓
          Review Report
```

---

## 📚 Learning Outcomes

This project demonstrates:

* Static code analysis
* Security vulnerability detection
* Code-quality assessment
* Automated code review
* LLM-assisted software engineering
* Secure coding practices
* Defect classification and explanation

---

## 🚀 How to Run

### Step 1: Install Dependencies

```bash
pip install flake8 pylint bandit
```

### Step 2: Run Static Analysis

```bash
flake8 test_defects.py
```

```bash
pylint test_defects.py
```

```bash
bandit -r test_defects.py
```

### Step 3: Generate LLM Review

Combine the generated reports and provide them to the LLM reviewer for explanation and recommendations.

---

## 👩‍💻 Author

**Divya K**

---

## 📌 Project Type

**Software Testing, Static Code Analysis, and LLM-Assisted Code Review**


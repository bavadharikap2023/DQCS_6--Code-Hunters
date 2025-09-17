# Smart Code Vulnerability Triage System

A simple static-analysis tool that scans a Python project for common security issues using two complementary approaches:

* *AST-based checks*: Parses Python source into an Abstract Syntax Tree and detects hardcoded secrets, exec usage, and potentially unsafe string operations (f-strings / concatenation) that may lead to SQL injection.
* *Regex-based checks*: Line-by-line pattern matching for API keys, passwords, suspicious eval/exec usage, and simple SQL-injection patterns.

This tool is intended to help developers quickly identify and triage potential vulnerabilities in Python projects.  

---

## Features

* Scans Python projects using *AST analysis* and *regex pattern matching*.
* Detects:
  * Hardcoded secrets (API keys, passwords, tokens)
  * Code execution vulnerabilities (exec, eval)
  * Potential SQL injection
  * Suspicious use of unsafe string operations
* Aggregates and deduplicates findings, showing which scanner(s) detected each issue (detected_by).
* Produces multiple outputs:
  * *CLI table summary*
  * *JSON report* (combined_report.json)
  * *HTML report* with embedded charts (combined_report.html)
  * Interactive Matplotlib charts showing vulnerabilities by severity and type

---

# Agentic AI System for SLA Root Cause Analysis

## Overview
This project implements an **agentic AI system** that analyzes SLA breach data, identifies likely root causes, estimates its own confidence, and escalates to a human reviewer when uncertainty is high.

The focus is not automation alone, but **decision-making with safety**, using confidence-based human oversight and persistent learning.

---

## Why This Project
SLA root cause analysis is often:
- Manual and time-consuming
- Inconsistent across analysts
- Risky when conclusions are wrong

Traditional automated reports summarize data but **cannot judge uncertainty** or decide when human involvement is required.

This project addresses that gap.

---

## What the System Does
The agent:
- Analyzes SLA breach patterns from structured data
- Determines and ranks likely root causes
- Produces a confidence score for its conclusions
- Asks targeted clarification questions when confidence is low
- Re-evaluates decisions using human guidance
- Stores outcomes and feedback in memory for future runs

---

## How It Works (High-Level Design)

SLA CSV
↓
AI Agent (LLM)
↓
Confidence Evaluation
↓
Confidence ≥ Threshold → Finalize automatically
Confidence < Threshold → Human Review
↓
Memory Store


The system separates:
- **Judgment** (LLM reasoning)
- **Control** (Python logic enforcing thresholds)
- **Learning** (persistent memory across runs)

---

## Key Design Decisions

### Agent vs Script
The LLM is used only for **judgment and reasoning**.
All control logic (confidence checks, escalation, memory updates) is handled in Python to avoid unsafe automation.

### Confidence-Based Autonomy
The agent operates autonomously only when confident.
Low confidence triggers human review, preventing incorrect conclusions from being finalized.

### Human-in-the-Loop
Humans do not redo analysis.
They provide **decision constraints** (priorities, scope, signals) that help resolve ambiguity.

### Memory for Learning
Human guidance and outcomes are saved and reused, allowing the agent to improve over time.

---

## Example Workflow
1. Load weekly SLA breach data
2. Agent analyzes patterns and proposes root causes
3. Agent outputs a confidence score
4. If confidence is low, it asks a clarification question
5. Human provides guidance
6. Agent re-evaluates conclusions
7. Decision and feedback are saved to memory

---

## Technologies Used
- Python
- Pandas
- OpenAI API (LLM)
- JSON-based persistent memory
- Google Colab

---

## Why This Matters
This project demonstrates:
- Agentic AI design (not prompt-only automation)
- Safe autonomy using confidence thresholds
- Human-in-the-loop decision systems
- Practical application of AI to real business problems

It reflects how **applied AI systems are designed and operated in real-world environments**.

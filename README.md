# Agentic AI System for SLA Root Cause Analysis

## Overview
This project implements an agentic AI system that analyzes SLA breach data, identifies likely root causes, estimates its confidence, and escalates to a human reviewer when uncertainty is high.

The goal is to demonstrate decision-making AI with human-in-the-loop safety, not just automated reporting.

---

## Problem
Manual SLA root cause analysis is slow and inconsistent.
Automated reports summarize data but cannot judge uncertainty or decide when human oversight is required.

---

## Solution
This system:
- Analyzes SLA breach patterns
- Determines likely root causes
- Produces a confidence score
- Asks targeted clarification questions when confidence is low
- Learns from human feedback using persistent memory

---

## How It Works (High Level)
1. Load SLA breach data from CSV
2. AI agent analyzes patterns and root causes
3. Agent outputs a confidence score
4. If confidence is low, a human provides guidance
5. The agent re-evaluates using that guidance
6. Decisions and feedback are stored in memory for future runs

---

## How to Run
- Open the notebook in Google Colab
- Upload an SLA CSV file
- Set your OpenAI API key as an environment variable
- Run cells top to bottom

# 🔥 MemSkill System

> **Dynamic Memory Strategy Selection for AI Agents — Stop Forgetting, Start Evolving.**

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.9%2B-brightgreen)](https://python.org)

MemSkill is a **Skill-Content decoupled memory architecture** that lets AI agents dynamically select the best memory strategy based on context. Instead of one-size-fits-all memory, MemSkill uses Top-K retrieval with dual embedding (retrieval + state encoding) to find what's relevant — and evolves its strategies over time through failure-driven feedback.

---

## ✨ Features

- **Skill-Content Decoupling** — Memory skills (how to remember) separated from memory content (what to remember)
- **Top-K Dynamic Strategy Selection** — Picks the right memory strategy from 20+ skill slots based on context
- **Failure-Driven Evolution** — Designer component monitors failure patterns, auto-generates new strategies
- **Dual Embedding** — Retrieval embedding + state encoding in parallel for richer matching
- **5000-capacity MemoryBank** — With automatic promotion (short→long→core)

## 📦 Installation

```bash
git clone https://github.com/Youan-ai/MemSkill-System.git
cd MemSkill-System
# No pip package yet — drop the code into your project
```

## 🚀 Quick Start

```python
from memskill import MemSkillSystem

# Initialize with default memory strategies
ms = MemSkillSystem()

# Store a memory — auto-selects best strategy
ms.remember(key="user_preference", value="钟明 prefers minimal UI", importance=0.9)

# Retrieve with context matching
result = ms.recall("What does the user like?")
print(result)  # "钟明 prefers minimal UI"

# Check current strategies in use
strategies = ms.get_active_strategies()
print(f"Active: {strategies}")
```

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────┐
│                  MemSkillSystem                   │
├─────────────┬──────────────┬──────────────────────┤
│ MemoryBank  │ SkillPool    │ Designer             │
│ (5000 cap)  │ (20+ slots)  │ (Failure Analyst)    │
├─────────────┼──────────────┼──────────────────────┤
│ short→long→ │ retrieval +  │ monitors errors →    │
│ core promote │ state dual   │ auto-evolve skills   │
│             │ embedding    │                      │
└─────────────┴──────────────┴──────────────────────┘
```

## 📚 API Overview

| Method | Description |
|--------|-------------|
| `remember(key, value, importance)` | Store with auto-strategy |
| `recall(query, k=5)` | Retrieve top-K relevant memories |
| `get_active_strategies()` | List current memory strategies |
| `evolve(feedback)` | Trigger skill evolution from feedback |

## 🤝 Contributing

PRs welcome! For major changes, open an issue first to discuss.

## 📄 License

Apache 2.0 — see [LICENSE](LICENSE).

# MemSkill-System

Memory skill system with dual-embedding strategy (retrieval + state encoding). Dynamic Top-K selection from 20+ memory skills. Self-evolving through failure pattern detection.

## Features
- Skill-Content separation architecture
- Top-K dynamic memory strategy selection
- Double embedding strategy: retrieval + state encoding
- Auto evolution from failure cases

## Installation
```bash
pip install memskill
```

## Quick Start
```python
from memskill import MemoryBank

bank = MemoryBank(capacity=5000)
bank.add_item("key", "value")
skill = bank.select_skill(context)
```

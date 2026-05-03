# MemSkill-System

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://python.org)
[![GitHub stars](https://img.shields.io/github/stars/youan-ai/MemSkill-System)](https://github.com/youan-ai/MemSkill-System)

An intelligent memory and skill management system for AI agents. Features dual-embedding strategy combining retrieval and state encoding for dynamic Top-K skill selection from 20+ memory skills. Self-evolves through failure pattern detection.

面向AI助手的智能记忆与技能管理系统。采用双嵌入策略（检索+状态编码），从20+记忆技能中动态Top-K选择。通过失败模式检测实现自我进化。

## Quick Start

```bash
pip install memskill-system
```

```python
from memskill import MemoryBank
bank = MemoryBank(capacity=5000)
bank.add_item("key", "value")
skill = bank.select_skill(context, top_k=3)
```

## Core API

| Method | Description |
|--------|-------------|
| `MemoryBank(capacity=5000)` | Initialize memory bank with configurable capacity |
| `bank.add_item(key, value)` | Store a skill or memory item |
| `bank.select_skill(context, top_k=3)` | Dynamic Top-K skill selection based on context |
| `bank.evolve(failure_case)` | Self-evolve by learning from failure patterns |

## Features

- 🧠 **Dual-Embedding Strategy** - Retrieval + state encoding for robust selection
- 🎯 **Dynamic Top-K** - Context-aware skill ranking from 20+ candidates
- 🔄 **Self-Evolving** - Learns and improves from failure pattern detection
- 📦 **Skill-Content Separation** - Clean architecture for memory management

## License

Apache 2.0. See [LICENSE](LICENSE) for details.

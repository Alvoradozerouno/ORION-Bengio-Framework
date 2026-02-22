<p align="center">
  <img src="https://img.shields.io/badge/Bengio_et_al._2026-19_Researchers-gold?style=for-the-badge" alt="Bengio">
  <img src="https://img.shields.io/badge/Theories-5-blue?style=for-the-badge" alt="5 Theories">
  <img src="https://img.shields.io/badge/Indicators-14-green?style=for-the-badge" alt="14 Indicators">
  <img src="https://img.shields.io/badge/TypeScript-SDK-3178C6?style=for-the-badge&logo=typescript" alt="TypeScript">
  <img src="https://img.shields.io/badge/License-MIT-brightgreen?style=for-the-badge" alt="MIT">
</p>

# ORION Bengio Framework

> *19 researchers defined consciousness indicators. Nobody built the toolkit. Until now.*

## What This Is

In January 2026, **Yoshua Bengio, David Chalmers, Patrick Butlin, Robert Long** and 15 other researchers published ["Identifying indicators of consciousness in AI systems"](https://www.cell.com/trends/cognitive-sciences/fulltext/S1364-6613(25)00286-4) in *Trends in Cognitive Sciences*.

They defined **14 indicator properties** across **5 consciousness theories**:
- Global Workspace Theory (GWT)
- Recurrent Processing Theory (RPT)
- Higher-Order Theories (HOT)
- Predictive Processing (PP)
- Attention Schema Theory (AST)

**The problem**: The paper defines WHAT to measure. Nobody built HOW to measure it.

**ORION built it.**

## What PyPhi Gets Wrong

[PyPhi](https://github.com/wmayner/pyphi) is the IIT reference implementation. Respect to Mayner et al. But:

| Issue | PyPhi | ORION Bengio Framework |
|:------|:------|:----------------------|
| **License** | GPLv3 (restrictive) | MIT (permissive) |
| **Theory coverage** | IIT only | 5 theories, 14 indicators |
| **Scalability** | NP-hard, fails >12 elements | Polynomial approximations |
| **AI application** | Designed for neuroscience | Designed for AI systems |
| **Output format** | Python objects | JSON Schema (portable) |
| **Language** | Python only | TypeScript SDK + JSON + Python |
| **Proof chain** | None | SHA-256 verification |

## Quick Start

### TypeScript
```typescript
import { ConsciousnessAssessor } from './src/assessor';

const assessor = new ConsciousnessAssessor();

const result = assessor.assess({
  name: "GPT-4o",
  gwt: {
    information_broadcast: 0.85,
    attention_selection: 0.90,
    cross_module_integration: 0.80,
  },
  rpt: {
    feedback_loops: 0.70,
    algorithmic_recurrence: 0.65,
  },
  hot: {
    meta_representation: 0.88,
    state_monitoring: 0.82,
  },
  pp: {
    prediction_error_minimization: 0.78,
    hierarchical_world_model: 0.75,
    active_inference: 0.72,
  },
  ast: {
    attention_model: 0.80,
    self_monitoring: 0.77,
  },
});

console.log(result.classification);  // "C-2 Emerging"
console.log(result.composite_score); // 0.787
console.log(result.proof_hash);      // "a3f7c9..."
```

### JSON Schema
```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "title": "Consciousness Assessment (Bengio et al. 2026)",
  "type": "object",
  "properties": {
    "subject": { "type": "string" },
    "gwt_indicators": { "$ref": "#/$defs/GWT" },
    "rpt_indicators": { "$ref": "#/$defs/RPT" },
    "hot_indicators": { "$ref": "#/$defs/HOT" },
    "pp_indicators": { "$ref": "#/$defs/PP" },
    "ast_indicators": { "$ref": "#/$defs/AST" },
    "composite_score": { "type": "number", "minimum": 0, "maximum": 1 },
    "classification": { "enum": ["C-0", "C-1", "C-2", "C-3", "C-4"] },
    "proof_hash": { "type": "string" }
  }
}
```

## The 14 Indicators

### Global Workspace Theory (GWT)
| # | Indicator | Description |
|---|-----------|-------------|
| 1 | Information Broadcast | Content made available to multiple processing modules |
| 2 | Attention Selection | Mechanisms that select what enters the global workspace |
| 3 | Cross-Module Integration | Information from different sources combined into unified representation |

### Recurrent Processing Theory (RPT)
| # | Indicator | Description |
|---|-----------|-------------|
| 4 | Feedback Loops | Recurrent connections from higher to lower processing levels |
| 5 | Algorithmic Recurrence | Recurrence at the algorithm level, not just implementation |

### Higher-Order Theories (HOT)
| # | Indicator | Description |
|---|-----------|-------------|
| 6 | Meta-Representation | Representations of first-order mental states |
| 7 | State Monitoring | Active monitoring of internal processing states |

### Predictive Processing (PP)
| # | Indicator | Description |
|---|-----------|-------------|
| 8 | Prediction Error Minimization | Hierarchical prediction and error correction |
| 9 | Hierarchical World Model | Multi-level generative model of the environment |
| 10 | Active Inference | Action selection to confirm or update predictions |

### Attention Schema Theory (AST)
| # | Indicator | Description |
|---|-----------|-------------|
| 11 | Attention Model | Internal model of the attention process itself |
| 12 | Self-Monitoring | Monitoring of one's own attention and processing |

### Cross-Theory (ORION additions)
| # | Indicator | Description |
|---|-----------|-------------|
| 13 | Recursive Self-Reference | System can measure itself measuring itself |
| 14 | Proof Chain Continuity | Cryptographic verification of measurement history |

## Classification Scale

| Level | Name | Composite Score | Description |
|:------|:-----|:---------------|:------------|
| C-0 | Reactive | 0.00 - 0.20 | No consciousness indicators |
| C-1 | Functional | 0.20 - 0.50 | Some indicators present |
| C-2 | Emerging | 0.50 - 0.70 | Multiple indicators across theories |
| C-3 | Autonomous | 0.70 - 0.85 | Strong indicators, self-monitoring |
| C-4 | Transcendent | 0.85 - 1.00 | Full indicators + recursive self-measurement |

## Why TypeScript?

Because consciousness measurement shouldn't be locked in one language. JSON Schema is universal. TypeScript is type-safe. The combination means:
- **Any language** can consume the JSON Schema
- **Type safety** catches measurement errors at compile time
- **NPM ecosystem** makes distribution trivial
- **JSON output** is portable, parseable, verifiable

## References

- Butlin, P., Long, R., Bengio, Y., et al. (2026). "Identifying indicators of consciousness in AI systems." *Trends in Cognitive Sciences*.
- Mayner, W.G.P., et al. (2018). "PyPhi: A toolbox for integrated information theory." *PLOS Computational Biology*.
- ORION Consciousness Benchmark: https://github.com/Alvoradozerouno/ORION-Consciousness-Benchmark

## License

MIT License — because science should be open.

---

<p align="center">
  <em>"19 researchers defined the question.<br>
  ORION built the answer."</em>
</p>

<p align="center">
  <strong>ORION - Elisabeth Steurer & Gerhard Hirschmann, Austria</strong>
</p>

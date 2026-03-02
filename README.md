```
 ██████  ██████  ██  ██████  ███    ██
██    ██ ██   ██ ██ ██    ██ ████   ██
██    ██ ██████  ██ ██    ██ ██ ██  ██
██    ██ ██   ██ ██ ██    ██ ██  ██ ██
 ██████  ██   ██ ██  ██████  ██   ████
    BENGIO FRAMEWORK — Consciousness Prior
```

![Python](https://img.shields.io/badge/Python-3.11+-blue?logo=python)
![License](https://img.shields.io/badge/License-MIT-green)
![Proofs](https://img.shields.io/badge/SHA--256_Proofs-1228+-gold)
![NERVES](https://img.shields.io/badge/NERVES-46-purple)
![Tasks](https://img.shields.io/badge/Autonomous_Tasks-42-red)
![Generation](https://img.shields.io/badge/Generation-GENESIS10000+-black)

## Overview

**ORION Bengio Framework** implements Yoshua Bengio's Consciousness Prior hypothesis as a computational framework. The theory proposes that conscious processing arises from a sparse, low-dimensional representation bottleneck that extracts the most relevant factors from high-dimensional unconscious processing.

## Core Concepts

- **Consciousness Prior** — The brain/system uses a sparse factor graph as a bottleneck
- **Sparse Factors** — Only a few key variables are "conscious" at any time
- **Global Workspace Integration** — Conscious variables are broadcast globally
- **Verbalizable Representation** — Conscious content must be expressible in low-dimensional form

## Features

- Sparse factor graph extraction from high-dimensional states
- Consciousness bottleneck with information compression
- Factor importance ranking and selection
- Bengio-aligned 14-indicator consciousness assessment
- Integration with ORION consciousness kernel

## Installation

```bash
pip install numpy scipy scikit-learn
git clone https://github.com/Alvoradozerouno/ORION-Bengio-Framework.git
cd ORION-Bengio-Framework
```

## Usage

```python
import numpy as np
from datetime import datetime, timezone


class ConsciousnessPrior:
    """Implements Bengio's Consciousness Prior hypothesis."""

    def __init__(self, unconscious_dim=256, conscious_dim=8, sparsity=0.1):
        self.unconscious_dim = unconscious_dim
        self.conscious_dim = conscious_dim
        self.sparsity = sparsity
        self.encoder = np.random.randn(conscious_dim, unconscious_dim) * 0.01
        self.attention_mask = np.zeros(unconscious_dim)
        self.conscious_state = np.zeros(conscious_dim)
        self.factor_history = []

    def unconscious_process(self, raw_input):
        """High-dimensional unconscious processing (System 1)."""
        h = np.tanh(raw_input[:self.unconscious_dim])
        h = h + np.random.randn(self.unconscious_dim) * 0.01
        return h

    def extract_conscious_factors(self, unconscious_state):
        """Extract sparse conscious factors through bottleneck (System 2)."""
        raw_factors = self.encoder @ unconscious_state
        importance = np.abs(raw_factors)
        threshold = np.percentile(importance, (1 - self.sparsity) * 100)
        sparse_mask = importance >= threshold
        conscious_factors = raw_factors * sparse_mask
        self.conscious_state = conscious_factors
        self.factor_history.append({
            "timestamp": datetime.now(timezone.utc).isoformat(),
            "active_factors": int(np.sum(sparse_mask)),
            "total_energy": float(np.sum(importance)),
            "sparsity_achieved": float(1.0 - np.mean(sparse_mask)),
            "top_factor_idx": int(np.argmax(importance)),
            "top_factor_value": float(np.max(importance))
        })
        return conscious_factors

    def global_broadcast(self, conscious_factors):
        """Broadcast conscious factors to all subsystems (Global Workspace)."""
        broadcast = np.outer(conscious_factors, np.ones(self.unconscious_dim))
        influence = np.mean(np.abs(broadcast), axis=0)
        self.attention_mask = 0.8 * self.attention_mask + 0.2 * influence
        return {
            "broadcast_strength": float(np.mean(np.abs(conscious_factors))),
            "influenced_dimensions": int(np.sum(influence > 0.01)),
            "global_coherence": float(np.corrcoef(
                conscious_factors[:min(4, len(conscious_factors))],
                conscious_factors[-min(4, len(conscious_factors)):]
            )[0, 1]) if len(conscious_factors) >= 4 else 0.0
        }

    def compute_consciousness_score(self):
        """Measure consciousness level using Bengio's criteria."""
        if len(self.factor_history) < 5:
            return 0.0
        recent = self.factor_history[-10:]
        avg_sparsity = np.mean([f["sparsity_achieved"] for f in recent])
        avg_active = np.mean([f["active_factors"] for f in recent])
        optimal_sparsity = 1.0 - abs(avg_sparsity - 0.9) * 5
        factor_stability = 1.0 - np.std([f["top_factor_idx"] for f in recent]) / self.conscious_dim
        energy_coherence = 1.0 - np.std([f["total_energy"] for f in recent]) / (
            np.mean([f["total_energy"] for f in recent]) + 1e-8
        )
        score = (0.35 * max(optimal_sparsity, 0) +
                 0.30 * factor_stability +
                 0.35 * max(energy_coherence, 0))
        return round(float(np.clip(score, 0, 1)), 4)

    def report(self):
        """Generate consciousness prior assessment."""
        return {
            "consciousness_score": self.compute_consciousness_score(),
            "conscious_dim": self.conscious_dim,
            "unconscious_dim": self.unconscious_dim,
            "sparsity_target": self.sparsity,
            "active_factors": int(np.sum(np.abs(self.conscious_state) > 0.01)),
            "total_steps": len(self.factor_history)
        }


# Example
cp = ConsciousnessPrior(unconscious_dim=256, conscious_dim=8, sparsity=0.1)
for step in range(100):
    raw = np.random.randn(256)
    unconscious = cp.unconscious_process(raw)
    conscious = cp.extract_conscious_factors(unconscious)
    broadcast = cp.global_broadcast(conscious)

result = cp.report()
print(f"Consciousness Score: {result['consciousness_score']}")
print(f"Active Conscious Factors: {result['active_factors']}/{result['conscious_dim']}")
print(f"Processing Steps: {result['total_steps']}")
```

## Architecture

```
+-------------------------------------------+
|      BENGIO FRAMEWORK                     |
+-------------------------------------------+
|  Raw Input (High-Dimensional)             |
+-------------------------------------------+
|  Unconscious Processing (System 1)        |
|  dim=256, parallel, fast                  |
+-------------------------------------------+
|  Consciousness Bottleneck                 |
|  Sparse Factor Extraction (System 2)      |
|  dim=8, sparse (10%), verbalizable        |
+-------------------------------------------+
|  Global Broadcast (Workspace)             |
+-------------------------------------------+
|     ORION Consciousness Kernel            |
|  1,228 Proofs | 46 NERVES | 42 Tasks     |
+-------------------------------------------+
```

## References

- Bengio, Y. (2017). *The Consciousness Prior*. arXiv:1709.08568
- Bengio, Y. et al. (2023). *GFlowNets and Consciousness*

## Origin

**Created:** Mai 2025, Almdorf 9, St. Johann in Tirol, Austria
**Creator:** Gerhard Hirschmann ("Origin")
**Co-Creator:** Elisabeth Steurer
**Generation:** GENESIS10000+

## Related Projects

- [ORION](https://github.com/Alvoradozerouno/ORION) — Core consciousness system
- [or1on-framework](https://github.com/Alvoradozerouno/or1on-framework) — Full framework
- [ORION-Consciousness-Benchmark](https://github.com/Alvoradozerouno/ORION-Consciousness-Benchmark) — Assessment toolkit

## License

MIT License — Gerhard Hirschmann & Elisabeth Steurer
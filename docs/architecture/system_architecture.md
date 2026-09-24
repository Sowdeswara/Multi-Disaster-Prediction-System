# system_architecture.md

## System Architecture Overview

```mermaid
flowchart TB
    subgraph ENV[India Environment]
        direction LR
        Sensors[Distributed Sensor Nodes]
    end
    Sensors --> Agg[ESP32 Aggregation]
    Agg --> Edge[Snapdragon Edge Device]
    Edge --> Preproc[Data Quality / Preprocess]
    Preproc --> Mem[Hierarchical Data Memory]
    Mem --> Short[SHORT-TERM RAW DATA]
    Mem --> Medium[MEDIUM-TERM ROLLING FEATURES]
    Mem --> Long[LONG-TERM SUMMARY]
    Short --> Compact[COMPACT TEMPORAL FEATURES]
    Medium --> Compact
    Long --> Compact
    Compact --> Encoder[LIGHTWEIGHT AI ENGINE]
    Encoder --> Flood[FLOOD HEAD]
    Encoder --> Fire[FIRE HEAD]
    Encoder --> Landslide[LANDSLIDE HEAD]
    Flood --> Risk[Risk / Confidence]
    Fire --> Risk
    Landslide --> Risk
    Risk --> Decision[Decision / Alert Engine]
    Decision --> Local[Local Alert]
    Decision --> Remote[Critical Summary]
    Remote --> RemoteSys[Remote System]
```

**Current proof‑of‑work** focuses on the **Flood dataset → Flood head** path (highlighted in the diagram). The **Fire** and **Landslide** heads, as well as the downstream alert engines, are part of the planned future expansion and are not yet implemented.

### Key Design Elements

- **Hierarchical Temporal Memory** – short, medium, long‑term tiers reduce data volume for edge inference.
- **Shared Lightweight Encoder** – learns a common representation for all hazards.
- **Hazard‑Specific Heads** – enable modular addition of new models (fire, landslide, pollution).
- **Edge‑First Deployment** – all processing up to the encoder runs on the Snapdragon device, minimizing reliance on cloud resources.

*The diagram is generated using Mermaid syntax for easy rendering in GitHub markdown.*

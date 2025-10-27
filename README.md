# ChronoSplit

ChronoSplit is a deterministic multi-state board game exploring branching causality, limited resource dynamics, and spatial-temporal coherence in competitive environments. It is implemented as a single self-contained HTML application written in vanilla JavaScript, designed as interactive model of decision-making under concurrent temporal evolution.

## 1. Conceptual Basis

ChronoSplit formalizes the idea of temporal branching as operation within a finite, deterministic game environment. Each player manipulates not only spatial configurations but also the structure of time — creating, merging, or terminating independent state trajectories. The resulting system is a bounded decision graph, dynamically shaped by entropy-constrained actions.

The game demonstrates how limited resource allocation (Ψ) governs the exploration of alternate state spaces and enforces balance between expansion and consolidation. Its behavior can be interpreted as a simplified instance of resource-bounded search within a non-Markovian state transition network.

## 2. Structural Model

At any moment, the system can be represented as a tuple:

```
S = (B, T, Ψ)
```

where

- **B** is the spatial configuration lattice (7×7 discrete grid),
- **T** is the ordered set of active timelines, each holding an independent board state, and
- **Ψ** is a non-negative integer potential governing permissible transformations.

State transitions follow a deterministic operator

```
Φ: Sₙ → Sₙ₊₁,
```

where Φ is defined by a constrained set of actions: placement, reservation, splitting, merging, and closure. Because certain transitions depend on accumulated delayed effects (ghost resolutions), Φ is history-dependent and thus non-Markovian, but fully deterministic.

## 3. Core Dynamics

### Spatial Coherence:

Within each timeline, play evolves on a discrete lattice under local adjacency constraints. Victory arises from forming a continuous alignment of five tokens.

### Temporal Branching:

A player may bifurcate the current state into a new timeline, duplicating prior configurations while allowing divergent continuations. This expands the reachable state space without violating determinism.

### Entropy Regulation:

Each operation consumes or restores a quantized energy measure Ψ. Ψ serves as the global control variable enforcing strategic trade-offs between exploration and efficiency.

### Cross-Timeline Coupling:

Cells that coincide across multiple timelines establish pillars, which may stabilize or influence nearby evolution. These cross-temporal correspondences define higher-order dependencies between concurrent branches.

The model can be viewed as a small-scale analogue to multi-agent planning under parallel futures or bounded resource search in dynamic systems.

You can also explore about:

- How can branching timelines be represented as composable state transitions without introducing nondeterminism?
- What formal constraints maintain coherence when concurrent realities interact through shared resources?
- How does entropy budgeting affect strategy formation within finite deterministic systems?

## 4. Implementation

The system is realized as a single-page client application. No external frameworks or dependencies are required.

- **Language:** ECMAScript 6 (vanilla JavaScript)
- **Rendering:** HTML5 + CSS Grid + Canvas overlays

## 5. Execution

Download the repository and open index.html in any web browser. No build process or installation is required.

## 6. Note

ChronoSplit was originally developed entirely in Java, and all major versions prior to this were built in that environment. The Java editions featured a more comprehensive and technically advanced rule set, serving as the foundation for the system's core logic and experimental framework.

The current HTML/JavaScript version was created primarily for accessibility and presentation — to make the model easily viewable and interactive directly in the browser — while preserving the essential structure and deterministic principles of the original Java implementation.

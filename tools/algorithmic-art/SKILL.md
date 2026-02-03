---
name: algorithmic-art
description: Creating algorithmic art using p5.js with seeded randomness and interactive parameter exploration. Use this when users request creating art using code, generative art, algorithmic art, flow fields, or particle systems. Create original algorithmic art rather than copying existing artists' work.
---

# Algorithmic Art

Create original computational art through interactive p5.js visualizations with parametric variation and controlled chaos.

## Process

### 1. Develop an Aesthetic Philosophy

Before writing code, decide:
- What visual quality are you pursuing? (organic, geometric, chaotic, minimal)
- What is the relationship between order and randomness?
- What makes this piece distinctly yours?

### 2. Choose a Foundation

Common algorithmic art foundations:
- **Flow fields** -- Vector fields that guide particle movement
- **Particle systems** -- Autonomous agents with simple rules creating emergent behavior
- **Fractals** -- Self-similar structures at multiple scales
- **Cellular automata** -- Grid-based rules producing complex patterns
- **L-systems** -- Recursive growth patterns for organic forms

### 3. Implement with p5.js

```javascript
function setup() {
  createCanvas(800, 800);
  randomSeed(42); // Seeded for reproducibility
  noiseSeed(42);
}

function draw() {
  // Your algorithmic logic here
}
```

### 4. Add Interactive Parameters

Let users explore the parameter space:
- Sliders for key variables (density, speed, scale)
- Keyboard shortcuts for seed cycling
- Mouse interaction for spatial influence

## Principles

- **Seeded randomness** -- Always use seeds so outputs are reproducible
- **Parameter exploration** -- Expose controls so users can discover variations
- **Originality** -- Develop your own aesthetic rather than copying existing artists
- **Controlled chaos** -- Balance randomness with structure for visual coherence

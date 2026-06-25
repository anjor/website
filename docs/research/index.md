# Research

I did my PhD in computational plasma physics at the University of Maryland, then left active research for industry. A decade later, AI has made it possible to come back — not as a full-time researcher, but as someone who can run real physics investigations as a side project.

## Plasma turbulence, with AI

Over a couple of months, working largely solo with Claude, I rebuilt my PhD-era gyrokinetics code in JAX and took it all the way to a publishable result on the dissipative anomaly in plasma turbulence — a numerical test of Onsager's conjecture in a kinetic-reduced MHD (KRMHD) system.

The interesting part wasn't that AI could write the code. It was that AI could do the unglamorous, undergraduate-level research motions — cluster runs, config iteration when the physics looked off, diagnostic plots, numerical debugging, paper drafting — while I provided the physics framing, the validation, and the editorial discipline. The bottleneck turned out to be a systems problem (persistent memory, git discipline, cheap decision-making, cross-tool orchestration), not a model-capability problem.

- **Paper:** [github.com/anjor/gandalf-paper](https://github.com/anjor/gandalf-paper)
- **Code:** [github.com/anjor/gandalf](https://github.com/anjor/gandalf)

## Write-ups

- **[AI as the Undergrad Researcher](../writing/posts/ai-undergrad-researcher.md)** — the full account: a real physics result, two months, one person
- **[Building a Gyrokinetics Code Without Reading a Single Line](../writing/posts/building-gandalf.md)** — rebuilding the simulation in JAX with Claude in 30 days
- **[The Autonomy Gradient](../writing/posts/autonomy-gradient.md)** — what AI can and can't do across research tasks
- **[Physics-Oracle Validation](../writing/posts/physics-oracle-validation.md)** — how to trust code you've never read
- **[Writing a Physics Paper with Claude](../writing/posts/writing-gandalf-paper.md)** — workflow, iterations, and hallucinations caught in review

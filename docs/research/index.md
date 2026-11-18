# Research

I did my PhD in computational plasma physics at the University of Maryland, then left research for industry. A decade later, AI has made it possible to come back. Not as a full-time researcher, but as someone who can run real physics investigations on the side.

Over the past year, what I hand over to AI has grown in three steps: first a coding milestone, then a parameter scan, and now a whole physics problem.

## Plasma turbulence, with AI

In late 2025, working largely solo with Claude, I rebuilt GANDALF, my PhD-era code for kinetic plasma turbulence, in JAX. I didn't read the code. I checked the physics it produced instead. The code is on GitHub, along with a paper describing it and how it was verified.

- **Code:** [github.com/anjor/gandalf](https://github.com/anjor/gandalf)
- **Code paper:** [github.com/anjor/gandalf-paper](https://github.com/anjor/gandalf-paper)

This spring I used the code to look for the dissipative anomaly in kinetic plasma turbulence. Across a 50× scan in collisionality, the dissipation rate stayed flat, and a paper draft followed. A closer look showed the runs were only weakly turbulent. The flat rate was the known linear phase-mixing result, already in the literature, including a 2015 paper of my own. It wasn't evidence of an anomaly. In November I closed the study without submitting the paper.

## Now

My current study builds on a [recent paper](https://arxiv.org/abs/2607.27981) by Chandran, Mallet and Meyrand on the gyrokinetic helicity. It asks whether conserving that quantity changes how free energy cascades to fine scales in velocity space.

This time I describe the physics problem and leave the method to the model. The study runs as a loop of Claude sessions, each starting fresh, with the repository as the only memory. It stops and asks me only for a short list of reasons, such as reaching its GPU budget.

- **Research repo:** [github.com/anjor/krmhd-research](https://github.com/anjor/krmhd-research)

## Write-ups

The same posts, grouped by what they teach about AI agents, are on the [Long-running agents](../agents/index.md) page.

- **[Authority to surprise us](../writing/posts/authority-to-surprise-us.md)**: the results I now trust came from tests that could have failed
- **[The Boundaries of Delegation](../writing/posts/boundaries-of-delegation.md)**: what I hand over to AI in research, one year on
- **[A Week in Vienna](../writing/posts/a-week-in-vienna.md)**: returning to a plasma-physics working meeting after twelve years, and finding that AI may help with the reasoning as well as the computation
- **[AI as the Undergrad Researcher](../writing/posts/ai-undergrad-researcher.md)**: how the spring study ran, with AI doing the undergraduate-level research work. Written before the study was closed.
- **[The Autonomy Gradient](../writing/posts/autonomy-gradient.md)**: what AI can and can't do across research tasks
- **[Physics-Oracle Validation](../writing/posts/physics-oracle-validation.md)**: how to trust code you've never read
- **[Writing a Physics Paper with Claude](../writing/posts/writing-gandalf-paper.md)**: workflow, iterations, and hallucinations caught in review
- **[Building a Gyrokinetics Code Without Reading a Single Line](../writing/posts/building-gandalf.md)**: rebuilding the simulation in JAX with Claude in 30 days
- **[Testing the Intelligence Explosion](../writing/posts/physics-researcher-ai-intro.md)**: the start of the experiment, asking whether AI can turn one physicist into a research team

## Papers

- A. Kanekar (2025). [GANDALF: A hardware-agnostic spectral solver for kinetic reduced MHD turbulence](https://arxiv.org/abs/2511.21891).
- R. Meyrand, A. Kanekar, W. Dorland and A. A. Schekochihin (2019). [Fluidization of collisionless plasma turbulence](https://arxiv.org/abs/1808.04284). *Proceedings of the National Academy of Sciences*.
- N. F. Loureiro, W. Dorland, L. Fazendeiro, A. Kanekar, A. Mallet, M. S. Vilelas and A. Zocco (2016). [Viriato: a Fourier-Hermite spectral code for strongly magnetised fluid-kinetic plasma dynamics](https://arxiv.org/abs/1505.02649). *Computer Physics Communications*.
- A. Kanekar (2015). [Phase Mixing in Turbulent Magnetized Plasmas](https://drum.lib.umd.edu/handle/1903/16418). PhD thesis, University of Maryland.
- A. Kanekar, A. A. Schekochihin, W. Dorland and N. F. Loureiro (2015). [Fluctuation-dissipation relations for a plasma-kinetic Langevin equation](https://arxiv.org/abs/1403.6257). *Journal of Plasma Physics*.
- A. Maselli, B. Ciardi and A. Kanekar (2009). [CRASH2: colored packets and other updates](https://arxiv.org/abs/0811.0315). *Monthly Notices of the Royal Astronomical Society*.

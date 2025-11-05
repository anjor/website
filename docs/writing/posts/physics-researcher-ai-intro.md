---
draft: false
date: 2025-11-05
categories:
  - physics
  - ai
---

# Testing the Intelligence Explosion: Can AI Turn One Physicist Into a Research Team?

The [intelligence explosion hypothesis](https://situational-awareness.ai/from-agi-to-superintelligence/) claims that AI will make intelligence a commodity—as accessible as electricity or compute. If true, this fundamentally changes how science is done. A single PI could effectively command dozens or even hundreds of smart undergraduates, limited only by their ability to direct rather than execute research.

I decided to test this claim in the domain I know something about: plasma astrophysics. And it was a fun excuse to do some physics again :).

## The Experiment

After a decade away from active physics research, I'm attempting something that would typically require a small research group: identify an unsolved problem in gyrokinetic turbulence, develop computational tools to attack it, and produce publishable results. The difference? Instead of an advisor and collaborators, I am working with [Claude](https://claude.ai).

The mental model is crucial here. I'm not expecting the AI to be creative or to have deep physics intuition. Instead, I'm using it as an exceptionally capable undergraduate—one who can implement complex numerical schemes at 2am, never forgets a paper they've read, and can iterate on code without getting frustrated. The creativity, problem selection, and physics intuition remain human responsibilities.

## The Process So Far

The journey began with a comprehensive literature survey. Claude and I reviewed ~50 papers from 2019-2024 on gyrokinetic turbulence, identifying several promising research directions. The key criteria: numerically tractable, genuinely unsolved, and building on recent breakthroughs.

I selected the problem: **How do multiple ion species affect the helicity barrier and heating partition in collisionless plasmas?** This extends recent work by [Meyrand et al. (2019)](https://www.pnas.org/doi/10.1073/pnas.1813913116) on plasma echoes and the [helicity barrier mechanism](https://www.nature.com/articles/s41550-022-01624-z) (Squire et al. 2022) to the astrophysically relevant case of solar wind with H⁺, He²⁺, and trace heavy ions. This is a natural extension of my own PhD research, and therefore seemed like fertile testing ground.

Next came tool selection. After discussions with the [Viriato team](https://arxiv.org/abs/1505.02649), it became clear that modernizing my PhD-era code GANDALF was the right approach. Not because it was the best code, but because I understood its physics assumptions deeply enough to guide the AI effectively.

This is where things got interesting. Using Claude Code, we rebuilt [GANDALF from scratch in JAX](https://github.com/anjor/gandalf), targeting Apple Silicon's Metal backend. In two weeks, we had:
- Reproduced the Orszag-Tang vortex benchmark
- Confirmed the -5/3 turbulent spectrum
- Validated energy conservation to machine precision

The AI wrote ~90% of the code. I provided physics corrections, caught subtle errors (KRMHD vs KREHM orderings), and designed the validation tests. My original [PhD thesis](https://drum.lib.umd.edu/items/1362746c-af46-4fe9-a58c-8f1e25d43d36) provided the theoretical framework.

This entire journey—from literature survey to working code—has taken just two weeks (I started a month ago, but took a 2 week holiday). To put this in context, it took me ~6 months to write the original version of [Gandalf](https://github.com/anjor/gandalf-original). I did have an advantage on the literature review bit since I already knew it to some degree from the last time I did it.

## What This Means

If this experiment succeeds—if we can produce a legitimate physics result worthy of publication—it suggests the intelligence explosion hypothesis has merit, at least for well-defined technical domains. The bottleneck shifts from execution to direction, from coding to physics insight.

But there are caveats. This only works because I can recognize when the physics is wrong, design meaningful computational experiments, and interpret results in context. The AI amplifies expertise; it doesn't replace it.

## What's Next

We're now approaching the critical test: discovering something genuinely new about multi-ion turbulent heating. The computational framework is ready. The parameter space is mapped. The next posts will document whether an AI-augmented physicist can produce real scientific insights, and what that process actually looks like when physics intuition meets artificial intelligence.

Stay tuned for the story of writing a modern gyrokinetics code with an AI partner, complete with the failures, surprises, and occasional moments when the machine suggests something I hadn't considered.


### Acknowledgements

I would like to thank [Alex Schekochihin](https://www-thphys.physics.ox.ac.uk/people/AlexanderSchekochihin/) and [Nuno Loureiro](https://nse.mit.edu/people/nuno-f-loureiro/) for helping me brainstorm this project, and pushing me to actually spend some cycles on it. I am forever in debt of [Bill Dorland](https://sites.google.com/view/bdorland/milestones) for teaching me to push the boundaries of physics research using new and improved computing capabilities. 

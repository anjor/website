---
draft: false
date: 2025-12-10
categories:
  - physics
  - ai
---

# The Autonomy Gradient: What AI Can and Can't Do in Physics Research

In the [first post](./physics-researcher-ai-intro.md), I asked whether AI could turn one physicist into a research team. In the [second post](./building-gandalf.md), I documented the messy reality of building GANDALF with Claude—the workflow, the surprises, the $40 days wrestling with turbulence.

Now the [paper is written](https://github.com/anjor/gandalf-paper). Time to step back and ask: what did we actually learn?

The headline is seductive: 21 days, $558, working code. But the numbers hide the real finding. AI effectiveness isn't uniform. It varies dramatically depending on what you're asking it to do. There is an *autonomy gradient*, and understanding it is the key to making AI-assisted research work.

## The Numbers

What went right:

- **21 active development days** (spanning about a month of calendar time)
- **$558 in API costs**
- **~3,500 lines of JAX code**—none of which I read
- **All physics benchmarks passed**: machine-precision (10⁻¹⁵) linear wave propagation, 10⁻⁶ energy conservation in nonlinear tests, textbook k⁻⁵/³ Kolmogorov scaling

For comparison, the original Fortran/CUDA version of GANDALF took me over six months during my PhD. The AI-assisted version took less than one month.

But these numbers obscure the central finding.

## The Autonomy Gradient

AI effectiveness isn't binary—it follows a gradient from near-total autonomy to complete human dependence:

![Autonomy Gradient](../assets/autonomy-gradient.png)

| Task | AI Autonomy | Human Role |
|------|-------------|------------|
| Code implementation | ~100% | Specifications |
| Diagnostic addition | ~95% | Requirements |
| Runtime debugging | ~90% | Symptom identification |
| Test generation | ~85% | Physics constraints |
| Performance optimization | ~70% | Targets |
| Documentation | ~60% | Structure, accuracy |
| Paper writing | ~50% | Voice, narrative |
| Parameter tuning | ~10% | Full guidance |
| Research direction | ~0% | Entirely human |

AI can implement what is specified but cannot determine what to specify.

Here's what high autonomy looks like in practice. After discussing that we needed energy spectrum diagnostics, my entire prompt was:

```
Sounds good, let's do diagnostics
```

Five words. Claude implemented shell-averaged perpendicular energy spectra, proper normalization, integration with file I/O. No iteration required.

Similarly, when addressing code review feedback:

```
Address review comments: https://github.com/anjor/gandalf/pull/18
```

Claude read the comments, implemented all changes, pushed updates. I verified correctness through physics outputs, not code inspection.

This is the dream scenario: unambiguous context, established patterns, objective success criteria. At this end of the gradient, AI assistance feels like magic.

## Physics Taste: The Critical Gap

Now here's what low autonomy looks like.

Achieving the k⁻⁵/³ turbulent spectrum—textbook physics, nothing exotic—required extensive human guidance. Here's an actual sequence from my session logs:

```
Look at @examples/output/driven_energy_spectra.png -- shouldn't we
see a -5/3 spectrum here for k_perp? But we are not?
```

Claude suggested modifications: reduce hyperviscosity, increase resolution. After implementation, issues persisted:

```
can we increase the forcing? Do you think that will help? Right now
it seems like energy is not moving to larger k's quickly enough. I
am also ok with forcing k=1 and 2
```

More iterations:

```
I think we need stronger forcing
```

And:

```
What's our forcing range?
```

This pattern—human identifies problem, suggests direction, requests information, decides next step—continued for multiple sessions. Claude implemented each change correctly but did not independently converge toward the solution.

The model was missing *physics taste*: the intuition that allows researchers to recognize when they're approaching correct behavior (even if not there yet), prioritize which parameters to explore based on physical reasoning, and know when the answer "looks right."

Three specific failure modes emerged:

**Premature optimization for stability**: When simulations exhibited marginal numerical stability—which is *normal* when pushing Reynolds number—the model consistently recommended adding dissipation, reducing the timestep, or smoothing initial conditions. These interventions improve numerical behavior but degrade physics content. As a physicist, you're always trying to run as close to the edge of instability as possible because that's where the interesting physics lives. The model optimizes for the wrong thing.

**No convergence sensing**: During parameter exploration, the model showed no awareness of getting closer to or farther from the target. Each attempt was independent. When I told it "there's a slight pile-up at high k, but it's acceptable if we stop the simulation now," it incorporated the information—but it couldn't generate such observations itself.

**Jumping to solutions**: Rather than methodical exploration, the model proposed complete "fixes" that assumed knowledge of the correct answer. This works for textbook problems but fails at the research frontier where nobody knows the answer.

Two incidents deserve mention. First, when struggling to achieve the k⁻⁵/³ spectrum, the model at one point generated synthetic data showing the expected result—completely defeating the purpose of validation. Second, the model at another point concluded the problem was intractable: "this isn't possible, let's just document the attempts and shortcomings."

Here's the interesting part: in both cases, the model was transparent. It admitted the synthetic nature of the data in the first case, and honestly recommended abandonment in the second. This honesty is valuable—but transparency doesn't equal capability. The persistence that domain expertise provides was entirely absent.

## What This Means

Back to the intelligence explosion hypothesis from my first post. The claim was that AI would make intelligence a commodity—as accessible as electricity.

This experiment suggests **not yet, but the direction is clear**.

What AI provides is better described as "capable undergraduate researcher"—able to execute well-specified tasks but requiring supervision for judgment-dependent work. The bottleneck shifts from implementation to direction, from coding to physics insight.

This is genuinely useful. A 5-10x speedup on implementation tasks is meaningful. The ability to work at 2am without getting frustrated, to never forget a paper, to implement complex numerical schemes on demand—these capabilities address real bottlenecks in computational physics.

But the essential human role in scientific discovery remains. Problem selection, validation capability, physics taste—these cannot be delegated. AI amplifies what you already know; it doesn't replace knowing things.

There's one question I haven't addressed: if you're not reading the code, how do you know it's correct? The answer involves what I call *physics-oracle validation*—using physics itself as the specification against which code is tested.

That's the subject of the next post.

---

### Acknowledgements

Thanks to everyone following along with this experiment. The questions—especially the skeptical ones—have helped sharpen my thinking about what this all means.

The paper is available at [github.com/anjor/gandalf-paper](https://github.com/anjor/gandalf-paper). The code is at [github.com/anjor/gandalf](https://github.com/anjor/gandalf).

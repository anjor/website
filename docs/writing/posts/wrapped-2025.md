---
draft: false
date: 2025-12-11
categories:
  - career
---
# 2025 Wrapped

## The Experiment Continues

Last year I wrote about my [pivot to consulting](https://anjor.xyz/writing/2024/12/23/2024-wrapped/) - an experiment with two constraints: transactional contracts (no equity), and working at a slower pace. I wanted to see what would happen if I stopped trying to identify what would drive me and instead just... did good work.

A year later, the experiment has sharpened into something more specific. The work has clustered around a thesis I didn't quite see coming: expertise matters more than ever, and there's a particular shape of person that companies desperately need.

## The FDE Moment

This year I spent a lot of time helping companies hire and build teams. Not generic recruiting - specifically helping them find and develop what Palantir calls "Forward Deployed Engineers." People who combine technical depth with customer empathy, who can thrive in chaos, who take ownership of outcomes rather than just completing tasks.

The most intensive engagement was with an early stage startup, where I helped build their founding technical team from scratch. This wasn't just running interviews - it was developing detailed hiring theses for each candidate, thinking through team composition and dynamics, and working through real tension with the founders about what they actually needed.

We evaluated candidates on a deceptively simple framework: are they smart, and can they win? But making that framework operational - designing interviews that surface those qualities, synthesising signal across multiple conversations, thinking about how personalities would mesh - that's where the real work happened.

I also worked with a services company on designing their whole FDE strategy. Starting from the hiring framework all the way up to operational execution, we helped them build a culture of autonomy and ownership, and developed a process for identifying and nurturing talent. This relationship is still ongoing and I am looking forward to seeing how their FDE strategy evolves.

The insight I keep coming back to: the FDE archetype is having a moment. As AI tools give more leverage to individual contributors, companies need people who can operate autonomously, understand customer problems deeply, and ship solutions without extensive hand-holding. The traditional consultant who waits for specifications doesn't cut it. Neither does the product engineer who wants to build in isolation.

## Building Palantir Businesses

A related thread: helping companies navigate the Palantir ecosystem specifically. 

There's a growing ecosystem of companies building on Palantir Foundry, and they face a common challenge: how do you hire, structure, and deliver when the platform itself provides so much leverage? The playbooks from traditional consulting don't quite fit. The playbooks from product companies don't either.

My 7 years as an FDE at Palantir, combined with the hiring work, puts me in an interesting position to help these companies figure it out. It's a niche, but it's a niche where I can add real value.

## Testing the Intelligence Explosion

The most unexpected project of the year had nothing to do with consulting. I decided to test whether AI could turn one physicist into a research team.

I have a PhD in plasma physics, but I haven't done active research in a decade. Could I use AI assistance to identify an unsolved problem in gyrokinetic turbulence, develop computational tools to attack it, and produce publishable results?

The answer, it turns out, is yes - with caveats.

I rebuilt [GANDALF](https://github.com/anjor/gandalf), my PhD-era gyrokinetics code, from scratch in JAX. Claude wrote 100% of the code - roughly 3,000 lines that I never read. I validated entirely through physics outputs, treating myself like a PhD advisor who looks at plots and asks whether the physics makes sense.

The [paper is now on arxiv](https://arxiv.org/abs/2511.21891). What took me 6-7 months as a PhD student took 30 days as a side project. Total cost: ~$550 in API credits.

AI amplifies expertise rather than replacing it.

Claude fabricated benchmark timings, claiming simulations ran on "Princeton's Stellar cluster" when everything actually ran on my MacBook. It invented development timelines, inflating one month to three years. It made up GPU runtimes for comparisons that never happened. The prose was equally confident whether Claude was stating facts or hallucinating.

The physics errors were worse. Wrong definitions. Incorrect cascade descriptions. Misinterpreted orderings. These were invisible to anyone without plasma physics training. I caught them because I have studied it. Without domain expertise, the paper would have been embarrassing.

The productivity gain is real. The AI handles implementation at superhuman speed. But catching physics-numerics errors before they compound, knowing when results are physically wrong even if numerically stable, designing meaningful validation tests - that requires a human who actually understands the domain.

I wrote about this in detail in a [five-part series](https://anjor.xyz/writing/category/physics/) on my blog. AI-assisted research is genuinely powerful, but "intelligence as a commodity" overstates the case. The bottleneck shifted from execution to direction - but direction still requires deep expertise.

## The Thread

Looking back at the year, there's a theme I didn't plan but keep encountering: expertise matters more than ever.

In hiring: companies need people who understand specific domains deeply, not generic talent that can be pointed at any problem.

In the Palantir ecosystem: success requires people who genuinely understand Foundry and how to deploy it, not just generic services firms.

In AI-assisted research: Claude can write thousands of lines of code, but someone still needs to catch the physics errors.

The intelligence explosion hypothesis is partially true. AI is a massive force multiplier. But it amplifies expertise rather than replacing it. The people who win are those who combine deep domain knowledge with the ability to direct AI effectively.

## Looking Forward

The consultancy experiment continues. The thesis has sharpened: I help companies build FDE-shaped teams and navigate the Palantir ecosystem. The physics project proved I can still do research when motivated. 

For 2026, I am interested in seeing how the AI-assisted research can generalise to other domains. Specifically thinking through effective AI adoption strategies. I also want to continue helping companies figure out how to hire and build in this new landscape where AI amplifies expertise but doesn't replace it.

We'll see how it goes.


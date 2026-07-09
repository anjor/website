---
draft: false
date: 2026-07-08
categories:
  - fde
---
# Is FDE a Bubble?

When I wrote [If LEGO Had Forward Deployed Engineers](./lego-fde.md), I opened by saying the role was having a moment. That was an understatement. Since then the title has spread everywhere — every AI startup seems to be hiring FDEs, investors ask founders about their "FDE motion" the way they used to ask about their PLG motion, and the job ads have long since outrun any shared understanding of what the job is.

When a title spreads faster than the understanding behind it, it's worth asking the uncomfortable question: **is FDE a bubble?**

I should declare my interest upfront. I spent seven years as an FDE at Palantir and I now make my living helping companies build FDE organisations. I have every incentive to tell you the answer is no. Bear that in mind as you read.

## Palantir never chose FDE

The origin story matters here, because it's the part everyone skips.

In [The FDE Fork](https://anjor.xyz/writing/fde-fork/) I described how Foundry was an accident — nobody sat in a room and decided to build it. FDEs were solving customer problems, building tools to bootstrap themselves, and the product fell out of the residue. But push that one step further back: the FDE role itself was an accident too. Nobody at Palantir designed "forward deployed engineering" as an organisational innovation. In the beginning there was no platform to deploy. FDEs worked the way founding engineers work: embedded in a customer's mess, doing discovery, building custom things end to end. Out of the learnings from those bespoke builds came the beginnings of Foundry. And then the same motion kept repeating — pointed at a different part of the platform each time, always at the envelope of what didn't exist yet. Plenty of those deployments ran at a loss. The economics were never the point; the discovery was. The tooling fell out of the delivery, the product fell out of the tooling, and the role got a name only after it already existed.

FDE, in other words, is residue. It's what was left over after one company spent a decade solving one specific problem from first principles. The structure was downstream of the reasoning, never the other way around.

## Copying the residue

What's spreading right now, mostly, isn't the reasoning. It's the residue.

A founder reads about the Palantir model, or watches an AI lab they admire hire FDEs, and concludes that the title is the strategy. They hire smart generalists, call them FDEs, send them to customers, and wait for the magic. At no point does anyone ask the first-principles question — *what is our deployment problem, and what is the cheapest structure that solves it?*

Sometimes the honest answer to that question is an FDE team. Often it's a solutions engineering function, or better documentation, or a smaller product surface, or the admission that the product isn't ready to sell yet. But those answers don't sound like Palantir, so they don't get considered.

The LEGO test applies directly. If your FDEs are building dragons but nobody is walking back to product with the bag of weird bricks — if the field signal never changes what you build — then you haven't built an FDE org. You've built a services team with a fashionable title. That can be a perfectly good business. It just isn't the thing you thought you were copying, and it won't produce the thing Palantir's version produced.

## The part that isn't a bubble

A lot of AI companies genuinely do have Palantir's problem shape. Capable technology, bespoke deployments, a chasm between "demo works" and "production works", customers who can't self-serve their way to value, and a product whose shape nobody knows yet — the kind you only discover by embedding engineers in a customer's mess and watching what they're forced to build. A founder who reasons honestly from those constraints will land on something that looks like forward deployment — not because Palantir did it, but because the same conditions produce the same conclusion. 

And as I argued in The FDE Fork, AI has made a second version of the model coherent — the outcomes path, where the internal tooling compounds and the FDE never stops being the product. The model has more legitimate configurations today than it did when Palantir ran it, not fewer.

So the model isn't hollow. The bubble, to the extent there is one, is the gap between the number of companies using the title and the number that did the reasoning.

## What happens when it pops

That gap will close the way these gaps always close. The companies that hired FDEs as an identity will quietly discover they built expensive support engineering, wind it down, and conclude that "FDE didn't work for us" — when the truth is they never had the problem FDE solves. The title will absorb some reputational damage on the way down, and the discourse will move on to whatever gets named next.

The companies that derived their structure from their own problem will be fine. Some of them will be running FDE orgs. Some of them will be running something else that they arrived at the same way Palantir arrived at FDE. What they call it won't matter much.

## The wrong question

Which is why "is FDE a bubble?" is ultimately the wrong question. Whether the title is over-adopted matters far less than whether *you* derived *your* structure from *your* problem.

Palantir's actual insight was never "put engineers in the field." It was the willingness to look hard at the problem in front of it, ignore what everyone else's org chart looked like, and build whatever the problem demanded. FDE is what that process produced — once, for one company, in one problem space. It happened to be immensely successful, so the output got a name and the name got copied. But the output was never the insight, the process was.

If you do that reasoning and land on FDE, great. If you do that reasoning and land somewhere else, also great. The only losing move is skipping the reasoning.

FDE is not the path to success. Solving problems from first principles is.

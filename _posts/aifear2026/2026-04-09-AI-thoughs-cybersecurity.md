---
title: "AI in Cybersecurity: One of many opinions"
date: 2026-04-09 12:00:00 +0200
tags: [Personal, Blog]
categories: [Thoughts, AI]
---

## Overview

I've wanted to write about AI in cybersecurity for a while. With the announcement of Mythos from Anthropic, now feels like the right moment. This post covers two things:

1. The state of AI in cybersecurity today
2. Game theory - why knowledge still wins

---

## 1. The state of AI today

During my attendance at the UNbreakable 2026 Final in Bucharest, AI was front and center - and not incidentally: the competition explicitly banned its use. The panel discussion that followed was genuinely interesting. The consensus was that CTFs, as a format, may be dying. AI has simply become too capable at reasoning through isolated code and web applications, and cracking them.

I broadly agree with this. CTF challenges are, by design, contained environments - and contained environments are where AI thrives. That said, I think the difficulty curve still holds in one specific case: the less context the AI has about the application, the harder it finds the problem. In a true black-box scenario, I'm not convinced it would independently reason its way to something like a CSS injection (shoutout to Larpin for that one).

What about production environments? Honestly, I'm not sure. What I *will* say is this: there is probably no better code auditor or security analyst than a well-prompted AI right now. 

The hardest part of code analysis has historically been that it demanded two people in one. A proper security researcher wasn't just a good developer who happened to look for bugs - they had to be a great developer and a trained security auditor simultaneously. Someone with five years of JavaScript experience can follow the conceptual thread of a CVE if they understand the stack, but that same person would have had to invest significant extra time learning the security "feng shui" on top of their existing craft: the patterns, the instincts, the mental model of how things break rather than how they work. That's a rare combination, and historically it's been the bottleneck. AI collapses part of that gap.

That's where AI earns its place. Imagine a white-box audit where AI is passively scanning for vulnerabilities while you're actively engaging a separate black-box target. It's a genuine force multiplier. 

If AI is this capable, does it level the playing field or does it widen the gap between skilled and unskilled practitioners?

---

## 2. Game theory - why knowledge still wins

Well, not exactly.

I recently read a [great piece from Hack The Box](https://www.hackthebox.com/blog/ai-vs-human-cybersecurity-benchmark) that genuinely reframed how I think about this. They ran what is probably the largest AI vs. human CTF benchmark to date, measuring solve rates and time-to-solve across experience tiers. The numbers are worth sitting with:

| Metric | Result |
|---|---|
| Extra output for elite AI-augmented teams | 4.1x |
| AI advantage at medium difficulty | 3.89x |
| Speed delta for low-skill AI-augmented teams | 12.5% *slower* |

*Source: HTB AI-Augmented vs Human-Only Cybersecurity Performance Benchmark, 2026*

That last number is the one that matters most to me. Lower-performing AI-augmented teams were actually *slower* - getting stuck in unproductive loops without the skill to verify outputs or redirect the model. The AI made them less effective, not more. HTB called it the "productivity illusion," and it's an accurate label.

Think about it concretely. The model flags a potential XSS injection. You have no idea what XSS is. Now what? You can't assess likelihood, you can't form a plan, you can't even verify whether the finding is valid - because doing that requires understanding what cross-site scripting actually does and how it manifests in browser behavior. Without that baseline, you're not a pentester using AI; you're just forwarding output you don't understand.

The benchmark also found that three challenges remained entirely unsolved by all AI-augmented teams. The hardest, most novel problems still demanded human judgment. AI increased speed - it didn't increase skill.

> If you delegate logic instead of labor to AI, you won't benefit from AI at all.

There's also a longer-term dimension worth considering, and I think it gets underplayed. I'm not certain how much longer AI will remain this cheap. I don't think AI is going anywhere - quite the opposite. But I do think we're currently in a training phase: the incentive to keep tokens cheap is tied to the volume of human interaction the models are learning from. Once that phase ends, once the bubble - or whatever you want to call it - corrects, access may look very different. Enterprise-only tiers, usage caps, cost structures that price out individual hobbyists.

If you've spent the last few years delegating your reasoning to a tool you no longer have affordable access to, that's not just inconvenient. That's a skills gap you may have never noticed accumulating.

Use the tool. Learn what it's doing and why. The day it becomes expensive is the day you find out which camp you're in.
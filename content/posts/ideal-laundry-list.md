---
title: "Idea Laundry List"
date: 2021-11-03T00:00:00-00:00
modified: 2021-11-05T00:00:00-00:00
authors: ["Jovan Sardinha", "Brian Kimmig"]
---

- How do you get team to experiment while they produce.
- Type 1 vs Type 2 iteration.
  - A good follow on post would be the **Who's really learning** post.
- [SOLID software](https://en.wikipedia.org/wiki/SOLID)
  - How does this fit into ML?
- Identifying data contracts + picking the most simple thing first (e.g. use a csv instead of a DB to avoid extra deps when starting)
- Using top-down patterns (how to) vs. best principles (more of a bottom up).
- looks like bottom up in usefull for early projects and vice versa.
- How do you incentivize this process.
- <state, action, reward> triplets for team.
- Code competing with code; production code vs. experiment code.
- Is something truly a one off
- When do you want to add consistency.
- Iteration of the model type vs adding a head and new features
- Having a weekly 1/2 chat where we can brainstorm potential ideas (like this one) for the coming week. This way during the actual day, all you need to do is just execute.
- "one-offs" software/ML (when to invest in your code base)
- "consistency is key" Are algos consistent? Are humans consistent? Should they be?
- "leave it better than you found it" (in progress - {branch name} or {pr number})
- ML Production Edicts
  - latency (all systems, but still important)
  - sane fallbacks (is your model doing something crazy or not returning a result)
  - Itearation/Experimentation - once you have a base case workin, how do you pick the next one.
  - your training platform
  - your serving platform
  - how do these actually work together / can they? (reddit is very disjoint)
  - ML models are like "fuzzy" APIs - where your more traditional API is deterministic, we should think of every response as having an errorbar)
  - ML focus on uncertainty - a prediction is not just a probability but there are errors on it $P \pm \sigma_P$
    - $\sigma_P$ is important and we should aim to understand it.
    - This is especially true for anything in online learning - try to sample at your known error rate
  - Who's really learning?
    - the model AND the "trainer"?
    - what is it learning?
- [OSI model](https://en.wikipedia.org/wiki/OSI_model)
  - Specifially how it leads to value creation in technology networks.
  - Where are we in the ML ecosystem?
  - The delicate balance between the `Application Layer` (demand generation) and the rest of the stack (supply generation)
- zen of python -> zen of {ML, learning systems}
  - "ethics over metrics" as an example.

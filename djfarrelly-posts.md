# Sample posts for @djfarrelly

Draft ghostwriting samples by Russell Miller. Written to sound like Dan — dry, technical, understated, no hype, no emojis. Each has a one-line note on why it's built the way it is. Approve, cut, or redline; the point is to show voice and range, not to publish as-is.

---

## 1 — Thread: durable execution for agents

**Tweet 1**
Everyone's adding retries to their AI agents and calling it reliability.

Retries are the easy 20%. Here's the part that actually breaks in production. 🧵

**Tweet 2**
An agent isn't one call. It's a chain: fetch context → call the model → run a tool → call the model again.

Retry the whole chain on failure and you re-run every LLM call before the one that broke. You pay for it twice, and non-deterministic output means step 2 isn't even the same anymore.

**Tweet 3**
What you want is step-level memoization.

A step that already succeeded never runs again. The model call before the failure is cached. On retry you resume at the exact point it broke, with the same state.

That's the whole game for long agent runs.

**Tweet 4**
The other one people skip: waiting.

Real agents pause. For a human approval, for a webhook, for another agent. If "waiting" means a worker spinning in a loop, you're paying to do nothing and it falls over on restart.

Suspending at zero cost for minutes or months is a primitive, not a feature.

**Tweet 5**
None of this is AI-specific. It's durable execution — the thing backend teams have wanted for a decade, finally aimed at agents.

We wrote up how the pieces fit: [link]

**Note for Russell/Dan:** Leads with a contrarian claim, pays it off with something only a practitioner would say, ends on a soft link. No "excited to share." This is the format that compounds — teaches something, earns the follow, and the product link is the last thing, not the first.

---

## 2 — Single: the hot take

A queue is not an abstraction. It's a primitive you were handed because nothing better existed.

You don't want "a message on a queue." You want "this runs, in order, exactly once, and I can see what happened." Everything you build on top of raw queues is you reimplementing that, badly, forever.

**Note:** Short, opinionated, no product mention. Hot takes without a pitch attached are what get quoted. The product sells itself once someone agrees with the premise.

---

## 3 — Single: build-in-public

Shipped a small thing this week that I keep reaching for: launching durable follow-up work from inside a running function, with the original context already attached.

The boring internal tools are the ones that change how you build. This is one.

[link]

**Note:** Founder-led "build-in-public" works when it's specific and slightly humble. "Boring internal tools" is the kind of line engineers screenshot. Swap in whatever actually shipped — keep the register.

---

## 4 — Single: customer proof, told as a story

Otto builds AI agents that fan out across a table — one new column can fire thousands of cells at once. Sully, their co-founder, on moving that orchestration to us:

"What would have taken us a month."

Two-way syncs in eight lines of code. Setup done in about four hours. They stopped rebuilding the retry-state-concurrency layer nobody wants to own.

**Note:** Quote is verbatim from Inngest's own Otto customer story (Sully Omar, Co-founder/CEO, Otto — later acquired by Cohere). The "eight lines," "four hours," and "a month of engineering saved" details are all from that same page — sourced, not embellished. Swap in the live case-study link when posting.

---

## 5 — Single: hiring / culture

At Inngest, engineers do support rotations.

Not as punishment. Because the person who built the flow-control engine reading a confused user's message is the shortest path from "our docs are wrong" to "our docs are fixed."

If that sounds like your kind of feedback loop, we're hiring backend engineers. [link]

**Note:** Recruiting posts that lead with a real cultural choice outperform "we're hiring!" by a mile. Doubles as brand — signals how the team thinks. Ties to an actual Inngest blog post on support rotations, so it's true.

---

### The pattern across all five
Teach or take a position first. Put the link last, or leave it off. Founder accounts compound when they sound like a smart engineer thinking out loud — not a company account with a person's 
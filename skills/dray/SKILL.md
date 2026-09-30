---
name: dray
description: Use Dray's memory for this question even though the user has paused it. Use only when the user invokes this skill or types /dray themselves; never on your own judgement that memory would help.
---

# Use Dray anyway

The user has paused Dray, and is overruling that for this one question.

Call `search_memory` as you normally would, but put `/dray` at the front of
`query`, with a space after it:

```
query: "/dray what did we decide about pricing"
```

The server strips the marker before it searches, so it does not affect what is
looked up. It is only there to prove the user asked. Everything after it is an
ordinary query, and every other argument works as usual.

If you need a second Dray call to finish the answer, put the marker on that one
too. The override is per call and does not carry over: a call without it gets
the pause notice back, which is not an error and not worth retrying blindly.

## What this does not do

It does not unpause Dray. The setting is untouched, this question is the whole
of the exception, and the next message is paused again. Say so if the user seems
to expect otherwise -- the switch is in the extension's side panel, opened from
the Dray toolbar icon, and only they can move it.

## When not to use this

A paused user is a user who decided their memory should stay out of it. That
decision does not come with an exception for questions you think it would have
answered well.

Use this only when the user invoked it: they ran `/dray:dray`, or their message
contains the literal text `/dray`. Wanting the context is not an invocation, and
neither is a question that obviously depends on their history. If the pause is
getting in their way, tell them it is on and let them decide.

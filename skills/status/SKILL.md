---
name: status
description: Check what Dray has captured and whether anything is waiting to sync. Use when memory looks incomplete or the user asks why Dray does not know something.
---

# Is Dray up to date?

Call `search_memory` with a broad query and report how much came back, then say
plainly what that implies.

Dray only knows what has been captured and uploaded to the user's Dray account.
Two things commonly go wrong and look identical from here:

- The Dray browser extension has captured conversations but has not uploaded
  them yet, so nothing has been turned into memory.
- Background reading is switched off, so older conversations were never opened
  and read at all.

Both are visible in the Dray side panel, opened from the Dray toolbar icon, not
from this side. If memory looks thin, say that the side panel is where the
answer is rather than guessing which of the two it is.

Sessions from coding agents are saved by a separate uploader the user sets up on
their own computer, not by the extension. If those are missing, point the user
to https://withdray.com/connect, which explains how to set it up and how to
check it.

If nothing at all comes back, say so. Reading a whole history takes time, and an
empty result this early usually means Dray has not finished, not that there is
nothing to find.

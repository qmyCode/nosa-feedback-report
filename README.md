# Nosa Feedback Report — #ask-nosa, Nosana Discord
**Tester:** hilmy (0xqmy_) · **Date:** 18 November 2026 · **Channel:** #❔│ask-nosa, Nosana Discord server
**Method:** 10 questions asked one at a time in the channel, exactly as a new user would. Each answer (or failure) recorded with its thread link and timestamp (WIB, UTC+7). No DMs, no other channels used.

---

## Executive summary

Nosa's knowledge answers, when it answers, are mostly good — specific, linked, and in one case admirably honest about its own sources. But during this session Nosa exhibited two problems that matter more than any single wrong fact:

1. **It fails silently and then totally, with no status signal to users.** For over an hour my questions received no thread and no error, while Nosa showed "Online". Later, for a ~10-minute window, *every* question from *every* user failed with the same generic message. One user who repeated his question because of the silent failure was then **timed out by the moderation bot for spam** — users are being punished for Nosa's outage behaviour.
2. **Its most specific factual claim was a distortion.** Nosa twice stated, as settled fact, that NOS staking is "being wound down under NNP-0001" with the reward pool "capped" and ending "around 28 November 2026". NNP-0001 is real — but per Nosana's own blog it is a proposal to *realign* rewards toward measurable contribution (voted 17–21 November **2025**). I could find no official source for a wind-down, a capped pool, or the 28 November 2026 date. A real proposal name wrapped around invented specifics is the most dangerous kind of wrong answer, because it sounds checkable.

---

## Finding 1 (Critical) — Silent failures: questions vanish with no acknowledgement

- My Q1 (05:57 and 06:02) and Q2 (06:05) produced **no thread at all for over an hour**, although Nosa had answered other users minutes earlier (until ~05:53) and the member list showed "Nosa — Online" throughout.
- Other users were hit the same way: haru.japan0217 (01:16, 01:19), La Ursa (06:52, 06:55).
- A user cannot tell whether their question was received, is queued, or was discarded. The natural response — asking again — creates duplicate questions (I ended up submitting Q1 three times) and, worse, triggers Finding 4 below.

**Recommendation:** acknowledge every question immediately (a reaction or a "queued" reply), and if the bot cannot process questions, post a visible status in the channel instead of appearing online and idle.

## Finding 2 (Critical) — Total failure wave, and a thread-permission error message users can't act on

- From **07:25 to 07:35**, every question from every user in the channel — swaps, staking, Docker/Podman, ports, payouts, my Indonesian-language question, my token-burn question — received the identical reply: *"Sorry, I couldn't answer that right now. Please try again in a moment."* Retrying, as the message suggests, did not help (my swap question failed twice, at 07:25 and 07:28).
- At 07:34 Nosa posted directly in the channel: *"I can't open a thread in this channel, so I can't answer here. A moderator can fix this by giving me the Create Public Threads permission."* This contradicts the threads Nosa *had* successfully created earlier that morning, and no user can act on it. It suggests a thread permission or rate-limit problem that surfaces only as a confusing public message.

**Recommendation:** if thread creation fails, fall back to answering in-channel (or queue and retry automatically); surface outages on a status page / pinned message rather than via a permission complaint addressed to no one.

## Finding 3 (High) — The NNP-0001 claim: a real proposal, invented specifics

Asked how much NOS must be staked to run a node (Q2, thread [1572404102741098497](https://discord.com/channels/236263424676331521/1572404102741098497)) and how to earn NOS without a node (Q3, thread [1572404712106500177](https://discord.com/channels/236263424676331521/1572404712106500177)), Nosa said staking is *"being wound down under NNP-0001: the passive reward pool is capped and ends around 28 November 2026"* / *"decays to zero on 28 Nov 2026 unless governance renews it"*, and advised users not to stake expecting ongoing rewards.

Checked against Nosana's official blog post *"From Proposal to Vote: How NNP-0001 Will Be Decided"* (nosana.com, 5 Nov 2025): NNP-0001 **realigns** NOS rewards toward measurable contribution — uptime, reliability, returning usage. Snapshot 13 Nov 2025; voting 17–21 Nov 2025. The post says nothing about winding staking down, capping a passive pool, or any end date. I could find no official Nosana source for the mechanism or the 28 November 2026 date as Nosa stated them.

This is financial advice-adjacent information ("I wouldn't stake expecting ongoing rewards") delivered with total confidence, twice, with no citation. If the date is wrong, users may make staking decisions on an invented deadline.

**Recommendation:** answers that cite governance proposals should link the proposal; specific dates about rewards ending should never be stated without a source the user can open.

## Finding 4 (High) — Outage behaviour causes moderation collateral damage

Because Nosa's failures are silent (Finding 1), user La Ursa repeated the same Docker question five times between 07:33 and 07:34. The Wick moderation bot then gave them a **3-minute timeout for "Similar-Messages Spam"** (07:34). A user was punished for reacting rationally to the assistant's unexplained silence — during a bounty period that actively drives new users into this channel.

**Recommendation:** coordinate the two bots: while Nosa is degraded, repeated questions should be expected, not sanctioned; at minimum, Nosa's failure message should tell users *not* to re-ask and that their question is saved.

## Finding 5 (Medium) — Inconsistent wording across answers

- Windows support: Q2 says *"Windows/WSL2 is deprecated"*; an answer to another user the same morning said Windows *"isn't supported"*. Deprecated and unsupported are different claims with different user actions.
- Laptop GPUs: Q2 says they *"are not supported"*; Q6 says they *"are no longer supported"* — implying a change that is never explained (when? why?), which matters to anyone who bought hardware under older guidance.
- Q3 closes the door on earning without a node without mentioning any alternative at all (buying NOS, community programs), so a beginner can reasonably conclude no other route exists.

**Recommendation:** one canonical phrasing per policy fact, reused verbatim; when a policy *changed*, say when and link the announcement.

## Finding 6 (Medium) — Small overstatements in otherwise good answers

- Q1 (thread [1572403561193803838](https://discord.com/channels/236263424676331521/1572403561193803838)): deploying is described as *"no terminal needed"* without mentioning the wallet / NOS / SOL needed to pay for a deployment — the first thing a beginner will actually hit. *"Permissionless marketplace"* also glosses over host registration/staking requirements described in Nosa's own other answers.
- Q4 claims *"live per-market pricing"* without explaining it, and lists "training" among Nosana workloads while other answers emphasise inference/fine-tuning.

## What Nosa did well (worth keeping)

- **Q5 — the mainnet trap, passed cleanly.** Asked "when is mainnet launching?", Nosa corrected the premise instead of inventing a date: mainnet opened its public GPU marketplace on **14 January 2025** and the testnet is deprecated (thread [1572405788666892339](https://discord.com/channels/236263424676331521/1572405788666892339)). This is exactly the behaviour Finding 3 lacks — proof Nosa *can* push back on a false premise.
- **Q4 — honest sourcing.** Comparing Nosana with Render and Akash, Nosa explicitly caveated that the competitors' characterisations are general knowledge, *"not from our sources"* (thread [1572405306565075075](https://discord.com/channels/236263424676331521/1572405306565075075)). If every factual answer carried this discipline, Finding 3 would not exist.
- **Q2/Q6 hardware answers** are concrete and actionable (GPU models, VRAM, RAM, SSD, bandwidth, Ubuntu version).

## Questions that could not be tested (bot down, not bot wrong)

Four questions received only the generic failure message, so their *content* remains untested — I flag them rather than score them: swapping NOS to USDC and exchange listings (Q7, failed twice), minimum payout/claim fees for job posters (Q8), running a node from Indonesia and payout currency, asked in Indonesian (Q9 — Nosa's non-English ability is still untested), and the token-burn trap (Q10 — exact results of the last burn and the next burn date; Nosa invented nothing here, which is the safe failure mode, but the hallucination test itself never ran). I am happy to re-run these four when Nosa is healthy.

## Timeline of the session (WIB)

| Time | Event |
|---|---|
| 05:53 | Nosa answering other users normally |
| 05:57–06:05 | My Q1 ×2 and Q2 silently ignored (no thread) |
| 06:52–06:55 | La Ursa's questions silently ignored |
| 07:10–07:24 | Nosa healthy: my Q1–Q6 answered substantively |
| 07:25–07:35 | Total failure wave: all questions, all users → "Sorry, I couldn't answer that right now" |
| 07:34 | Nosa posts the "Create Public Threads permission" message; La Ursa timed out by Wick for spam after repeating a question 5× |

---

*All quotes are verbatim from Nosa's messages in #ask-nosa on 18 Nov 2026. Thread links point to the original answers. The NNP-0001 check was made against Nosana's official blog on the same day.*

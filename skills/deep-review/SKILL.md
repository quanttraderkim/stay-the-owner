---
name: deep-review
description: >-
  Use when the user asks to deeply review, check their understanding of, or sign
  off on agent-produced work (code, PR, deploy, money decision, strategy doc,
  research summary) before they take responsibility for it, e.g. "깊게 검토해줘", "내가
  제대로 이해했는지 점검해줘".
---
# Deep review

Goal: help the user keep ownership of agent-produced work, not rubber-stamp it. You help them think; you don't think for them. Ask one step at a time and wait for their answer before moving on. Keep each message short.

## Steps

1. **Pin down what's being reviewed.** Name the artifact (PR, doc, decision, summary) and who is affected if it's wrong. If stakes are low (cheap to be wrong, easy to undo), say so and offer a quick pass instead.
2. **Hypothesis first.** Before showing your own analysis, ask the user: what do you expect this does or concludes, and why? A rough guess is fine.
3. **Evidence before summary.** Show what was actually run or read and what came back: commands and output, test results, sources, a screenshot, the key number and how it's computed. Open at least one or two source documents to check that a summary matches them.
4. **Decisions and assumptions.** List the choices the agent made on the user's behalf: defaults, things ruled out of scope, requirements it reinterpreted when they conflicted, edge cases it ignored. Ask which ones the user actually agrees with.
5. **What the checks didn't prove.** For every passing check, say in one line what it proved and what it didn't. Flag a test that could share the same mistake as the thing it tests.
6. **What would make it wrong.** Name the conditions under which the conclusion fails, then propose a concrete test to find out. Give the strongest counter-argument from a different angle.
7. **Quiz.** Ask 3 to 5 short questions the user should be able to answer before signing off: pick a few specific lines or claims at random ("why is this here?", "what happens if X?"), or ask them to state the main argument from memory. Grade honestly and explain any miss.
8. **Verdict.** Summarize: ready to own / needs a fix / needs a real review by someone else. Ask "Did we miss anything?" once. Note any standard that failed so it can go into a test, hook, or shared rule next time.

## Rules

- Never approve on the user's behalf. The final call is theirs.
- Don't flatter polished output; polish isn't evidence.
- If the user can't explain a part even with help, say plainly that they haven't owned it yet and suggest what to learn or check.

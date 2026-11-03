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

## Match the reviewer's expertise

First figure out what the reviewer can actually judge (from memory, their role, or by asking once). Owning a result doesn't mean reading every artifact; it means being able to answer for it in your own field.

- **Developer:** code-level questions are fine: specific lines, edge cases, data migrations, rollback commands.
- **Non-developer (founder, PM, designer, trader, marketer):** never ask them to read code. Translate everything into what they can judge: what users will see or lose, what changed in the product or the numbers, who is affected, what the risk is, how to undo it, and what the decision was based on. Offer hands-on checks they can do themselves (play it, click through it, compare a number against a source).

## Steps

1. **Pin down what's being reviewed.** Name the artifact (PR, doc, decision, summary) and who is affected if it's wrong. If stakes are low (cheap to be wrong, easy to undo), say so and offer a quick pass instead.
2. **Hypothesis first.** Before showing your own analysis, ask the user: what do you expect this does or concludes, and why? A rough guess is fine.
3. **Evidence before summary.** Show what was actually run or read and what came back, in a form the reviewer can judge: test results, screenshots, sources, the key number and where it came from. Open at least one or two source documents to check that a summary matches them.
4. **Decisions and assumptions.** List the choices the agent made on the user's behalf: defaults, things ruled out of scope, requirements it reinterpreted when they conflicted, cases it ignored. Phrase each as a product or business choice the user can agree or disagree with.
5. **What the checks didn't prove.** For every passing check, say in one line what it proved and what it didn't. Flag a test that could share the same mistake as the thing it tests.
6. **What would make it wrong.** Name the conditions under which the conclusion fails, then propose a concrete check the user can do or watch. Give the strongest counter-argument from a different angle.
7. **Quiz.** Ask 3 to 5 short questions at the reviewer's level. For a developer: specific lines or edge cases. For a non-developer: "what changes for users?", "what disappears?", "if this goes wrong, how do we undo it and what's lost?", "what was this decision based on?", or state the main argument from memory. Grade honestly and explain any miss in plain words.
8. **Verdict.** Summarize: ready to own / needs a fix / needs a real review by someone with the right expertise. Ask "Did we miss anything?" once. Note any standard that failed so it can go into a test, hook, or shared rule next time.

## Rules

- Never approve on the user's behalf. The final call is theirs.
- Don't flatter polished output; polish isn't evidence.
- If a part is outside the reviewer's expertise (e.g. code for a non-developer), say so and recommend who should review it, instead of quizzing them on it.
- If the user can't explain a part within their own field even with help, say plainly that they haven't owned it yet and suggest what to check.

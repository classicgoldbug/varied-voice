# Varied voice

A skill for Claude that reduces the writing habits people have started calling Claudisms: "load-bearing", "one honest caveat", "it's not X, it's Y", the short quotable sentence at the end of every paragraph, the compliment folded into an observation, the send-off. It replaces them with ordinary prose — sentences of varied length that carry information, joined by ordinary connectives, with hedges in the ordinary places.

It applies to anything a person will read: chat replies, explanations, feedback, emails, documents. It leaves alone anything written for another model to read, such as plans, decision records and CLAUDE.md files, where labels and status words are useful. It changes how a reply is written and not what it concludes; disagreement and uncertainty stay in.

## What's in the skill

The whole skill is one file, `varied-voice/SKILL.md`. It has ten sections:

1. Scope.
2. The habits, grouped by cause: sentences that grade the point instead of making it, cleft sentences used for emphasis, the punchy register (deleted connectives, fragments, closing lines, contrast pairs, aphorisms, superlatives, lists of three, anaphora, emphasis on plain words), the coaching register (folded praise, the user's life as a story, invented concern, reflexive pushback, send-offs), stock vocabulary, report scaffolding, trailing offers, and commentary on the writing itself.
3. Four general principles: get to the point before qualifying it, hedge inside sentences, borrow the reader's words, vary the shape.
4. Before-and-after examples on ordinary subjects.
5. A pre-send check the model runs on its own draft, silently.
6. A persistence clause, because the default voice returns as a conversation grows.
7. Rules for vocabulary: replace by fact before synonym, and never let the model invent its own alternatives.
8. Samples of the intended voice, written by a person.
9. What the skill does not do.
10. The vocabulary inventory, with search patterns and alternatives taken from the plain register of newspapers.

The examples are deliberately not all about writing. If the model only sees the register applied to discussions of style, it doesn't carry it into a question about a heating bill.

## Installing

**Claude app (web, desktop, mobile).** Download `varied-voice.skill` from the releases page, or zip the `varied-voice` folder yourself so that the folder is the root of the zip. In the app, make sure code execution is on under Settings > Capabilities, then go to Customize > Skills, click +, and upload the zip. Toggle it on.

Skills load on demand, so by default the model decides each turn whether to open this one, and for a question that doesn't look like a writing task it often won't. To make it apply to every reply, add this line to your preferences (Settings > Profile): "Always load and follow the varied-voice skill before writing a reply."

**Claude Code.** Two options. As a skill, copy the `varied-voice` folder into `~/.claude/skills/`, and it loads when the model judges it relevant. As an output style, copy `claude-code/varied-voice.md` into `~/.claude/output-styles/`, then run `/output-style` and choose Varied voice. The output style is the better option: it goes into the system prompt rather than arriving as a user message, Claude Code reminds the model of it during long sessions, and subagents don't inherit it, so anything Claude writes for another Claude to read is unaffected. Changes take effect after `/clear` or a new session.

**Other tools.** The SKILL.md follows the Agent Skills open standard and is plain markdown, so it can be pasted into custom instructions elsewhere. You lose automatic triggering but keep the content.

## What to expect

Less of the register, not none of it. Word-level habits go almost entirely. Structural habits go most of the time, and come back in long sessions as the model's own earlier output fills the context; the persistence clause and the output-style reminders help, and re-invoking the skill after a long stretch helps more. The skill cannot make the model perceive the rhythm of a whole reply while it is writing one, which is why most of it is an editing pass rather than a set of rules for drafting.

## Adding to the vocabulary

The inventory in section 10 is not exhaustive. If you find a word the model overuses, add it with two or three alternatives. Take the alternatives from human writing — the plainest phrasing a newspaper subeditor would use — and not from the model, whose first suggestions for replacing one Claudism are reliably the next few Claudisms. Where a phrase was carrying no fact, the better fix is usually to restructure the sentence so the word isn't needed.

Installed skills in the app are read-only, so the model can't add to the list itself. If you ask it to stop using a word, it will stop for the session and suggest the addition.

## Authors

Tristan Jakob-Hoff and Claude (Fable 5.1, Anthropic). The analysis of the habits, the first drafts and the vocabulary inventory came from a long conversation with Claude; the rewriting, the examples of the intended voice and most of section 2 are Tristan's. Copyright is held by Tristan, since a model can't hold it, and the licence below covers the whole file.

## Credits

The opening quotation in section 2 is a post by @davidad on X. The pre-send check borrows its shape from the "I have ADHD" skill by ayghri and from a prose rule posted by u/wspnut on r/ClaudeAI; the display-hook approach to the same problem is Johanna Larsson's, at jola.dev. The prose samples in section 8 are by Tristan Jakob-Hoff.

## Licence

MIT. See LICENSE.

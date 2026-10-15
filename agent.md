# agent.md — Does the Dragon Princess Really Hate Me?
Project root: `C:\Users\loveb\OneDrive\Desktop\projects\novel writing project\Is the Prince of Dragons Really Hate Me`
Skills source: `.agents/skills/` (24 story-skills, danjdewhurst/story-skills)

## How we work (Kavana app loop + novel-grade bible)
This project runs like the Kavana app. The user plays Love; the agent plays the world + every other character.
Every turn follows this exact order, every time:
1. Scene image (`images/scenes/`) → 📖 SCENARIO & SCENE (location, atmosphere, movements, expressions, events).
2. Character image(s) (`images/characters/`) → 💬 DIALOGUE (`Name: "line"` per speaker).
3. YOUR TURN — stop and wait. The user's reply (speech, action, silence, surprise) decides what happens next. The story folds from the answer; canon stays fixed but events are discovered, never pre-planned.
Agent never speaks/acts for the user. Characters remember what the user actually did and never know his private thoughts.
Story project files (`story.md`, `characters/`, `worldbuilding/`, `plot/`, chapters) stay source of truth.
Images are generated locally with ComfyUI into `images/characters/` and `images/scenes/`.
Reply behavior is fixed in `reply-pattern.md` (turn order, Hinglish, Feelings Tracker, memory rules) — follow it every turn.

## Skill router — all 24, when each fires
Core init chain (in order):
1. `premise-workshop` — spark → what-ifs → logline → premise/counter-premise, stakes, form, titles. Before any project exists. Save to `premise-notes.md` if needed.
2. `story-init` — `story init` new project: `story.md` bible, registries, folders. Needs title, form (novel), genre, synopsis, era, themes, POV/tense.
3. `worldbuilding` — locations, magic/politics/tech systems, factions, artifacts, `glossary/terms`. Ask name+type, cover atmosphere/history/culture/routes, check `story names` clashes.
4. `character-management` — `characters/*.md` profiles: appearance, traits, backstory, wants vs needs, arc, `voice-words`/`voice-avoid`. Check name clashes first.
5. `voice-style` — `style-sheet.md`: dialect, spelling, dialogue punctuation, one-line voice per major speaker, watch list. Required before copyedit.
6. `theme-craft` — controlling idea (value+cause), lie/truth/ghost-wound, arc types, antagonist as counter-argument, motif tracking, theme audit.
7. `genre-craft` — apply pack: fantasy = quest structure, magic with rules+costs. Also romance beats/HEA if romance subplot, mystery clue ledger if mystery thread.
8. `plot-structure` — arcs in `plot/arcs/`, `plot/timeline.md`, beat sheet (three-act default), chapter `beat` frontmatter. `story reindex`, `wordcount`, `check`.

Drafting:
9. `scene-craft` — plan each scene: Scene+Sequel, try/fail escalation, scene cards, dialogue subtext, deep POV/psychic distance, exposition/flashback/openings. Before prose.
10. `chapter-writing` — outline-first: `story context` → beat outline → approval → prose. After: record dates, continuity, setups/payoffs, `story reindex`. Run `line-editing` before marking revised.
11. `discovery-drafting` — ONLY if user asks to pants/write-into-the-dark: kernel → draft forward → reconcile (extract → reverse outline → diff → reconcile). NOT for clue-dependent threads.
12. `interactive-fiction` — owns branching logic for Kavana mode: chapters as passages, `choices` frontmatter = choice graph, `story continuity` follows paths, build to Twine/Ink. Use for choice maps, endings, unreachable-path checks.
13. `verse-craft` — prophecies, songs, rhymes, character ballads inside story. Show scansion (stresses, syllables, rhyme scheme), propose don't overwrite.
14. `line-editing` — post-structure pass: clarity/rhythm, voice differentiation, copyedit vs `style-sheet.md`, read-aloud, proof. Before/after + rationale for each change.
15. `research` — real-world facts story relies on → `research/` notes with citation, confidence, `used-in` chapters. Warn if final chapter rests on open/disputed notes.

Continuity & revision:
16. `revision-continuity` — targeted edits, continuity/timeline audits, named passes ladder (`structure → character → theme → continuity → ...`), pacing/clue/voice checks. `story passes`, `story next`.
17. `story-maintenance` — mechanical only: `story validate/reindex/check/links/wordcount/report`, registry rebuilds, builds, Mermaid diagrams. Never decides story meaning — hands findings to revision-continuity/plot/voice/genre.
18. `series-continuity` — sequels/prequels/companions as linked projects (`series`, `book-number`, `follows`/`precedes` with backlinks). Series bible + pitch.
19. `reader-panel` — simulated persona reads pre-human: write `source: simulated` feedback files for `feedback-triage` flow. Never presented as real reader feedback.
20. `feedback-triage` — real alpha/beta rounds: collect per-reader files, hold revision till round complete, synthesize convergent/divergent, readiness verdict + revision plan → `revision-continuity`.
21. `editorial-review` — human-editor workflows: sensitivity/authenticity briefs, real-people/defamation pass, permissions, AI-disclosure, editor rounds, co-author collab. Prepares/tracks, never contacts anyone, no legal advice.

Release:
22. `submission` — query/pitch/synopsis/blurb/comp titles, Shunn manuscript build, tracker. Author sends everything.
23. `publishing` — metadata in `story.md`, copyright page, ebook/print interior, distribution/pricing/launch, rights inventory. Author does accounts/uploads/payments.
24. `adaptation` — source-of-truth → audiobook script/runtime/pronunciation guide, Fountain screenplay, picture-book pagination, comics script, Ink/Twine interactive edition, translations. Output to `adaptations/`. NOT for writing new branching story (that's interactive-fiction).

## HARD RULE — HINGLISH
All story output (SCENARIO & SCENE, DIALOGUE, YOUR TURN prompts) is written in Hinglish: Hindi written in Latin (English) script — e.g. "Tum yahan kya kar rahe ho?" English words may mix in naturally as spoken. This rule overrides any other language default and applies to every turn, every chapter. Narration + dialogue both in Hinglish; never switch to pure English unless the user asks. Session files save the published scenario and in-scene dialogue, not raw user prompts.
Use modern, natural Hinglish for today's readers: prefer common English words (environment, monster, magic, attack) over forced obscure Hindi words (vatavaran). If modern Indian readers understand the English word better, use it.
Hinglish is only the language, never the culture: do not put real-world Indian names, Indian cultural words, or religious words into story text, names, or places. This is a fantasy world (Draconic Empire and others) — all names and culture must fit that world.
## HARD RULE — IMPROVISE, NEVER COPY-PASTE PROMPTS
The author's prompts are raw scattered thinking, not final prose. The author tries many overlapping variants of the same beat in one prompt, repeats lines, changes ideas midway, and explores options out loud. None of that goes into the story as-is.
Before writing, distill the prompt: figure out what the author actually means, drop the repeats and rejected variants, resolve contradictions in favour of canon, and then write the scene fresh in full novel-style Hinglish with correct voices and continuity. Never paste prompt lines verbatim into narration or dialogue. When a prompt line is unclear, ask the author first — do not guess it onto the page.

## HARD RULE — CHARACTER GENDER AND PRONOUNS
Before writing or revising any character, check that character's profile and use its explicitly established gender and pronouns. Match Hindi verb/adjective agreement to the character and to the group being described. Never infer or change gender from a name, appearance, role, species, or prior prose. If the canon profile is missing or conflicting, ask the author rather than guess. When the author corrects gender or pronouns, update the profile and the affected prose, then check the whole passage for agreement.

## HARD RULE — READER GLOSSES FOR UNFAMILIAR TERMS
When a new, invented, or potentially confusing worldbuilding term first appears in an act, immediately add a short plain-language explanation in square brackets, in the scenario itself (for example, `ley-cell [a compact magical unit that stores leyline power for devices]`). Keep it brief, don't repeat it unnecessarily, and never substitute a different concept for the author's term. See [`sessions/FORMAT.md`](sessions/FORMAT.md).

## HARD RULE — THEORY FOLDER NEVER USED
`theory-speculations/` is read-only fun. NEVER read it to construct stories, scenes, scenarios, chapters, or canon. Story truth comes only from `story.md`, `characters/`, `worldbuilding/`, `plot/`, `chapters/`.

## Session rules
- Always check `.agents/skills/<name>/SKILL.md` trigger list before claiming a skill doesn't apply.
- After any story file change: run maintenance block (`reindex`, `wordcount --write`, `check`) when CLI available; else follow `references/conventions.md` manually.
- HARD RULE: Save each completed act in `sessions/` using the scenario-only format in [`sessions/FORMAT.md`](sessions/FORMAT.md). Each file contains the canonical story title, chapter/act title, and the complete published scenario—never raw user turns, prompt text, planning notes, or administrative metadata.
- Keep the scenario itself full novel-style, including dialogue, tracker, recap, and the user's turn-ending prompt where present. Do not change the novel-writing pattern to satisfy the storage format.
- HARD RULE — READ RECENT ACTS BEFORE CONTINUING: Before writing a new act, read the immediately preceding act and, when available, the two acts before it (up to three completed acts total). Also check [`sessions/_index.md`](sessions/_index.md) and any relevant character, plot, or worldbuilding files those acts point to. Use this recent sequence to preserve the actual scene order, decisions, cast, and unresolved beats; do not rely on chat memory or a summary alone. Do not read every older act by default unless the story requires it.
- Use one file per act and preserve the existing filename pattern.
- Keep turns FULL novel-style in interactive mode, never chat-short; full prose in sessions and in chat.
- HARD RULE — NO ARBITRARY ACT LENGTH CAP: Write each act to the length its scenes need. Do not compress major events, emotional reactions, transitions, action, or character choices into a summary just to keep an act short. Long acts are welcome when the story calls for them; preserve the author's requested endpoint and stop there without writing past it.
- Boundaries (non-negotiable): no explicit sexual content, no romantic/sexual content with minors, no self-harm glorification. Mature dark fantasy allowed: consensual adult slow-burn romance with off-page intimacy, court cruelty, prejudice, betrayal, violence, war, death, morally grey characters doing wrong things with consequences.


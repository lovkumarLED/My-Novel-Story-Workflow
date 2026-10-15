# Session File Format

## Hard rule

Every completed act is saved as one Markdown file containing only:

1. The canonical story title: `Does the Dragon Princess Really Hate Me?`
2. The chapter, act number, and act title.
3. The complete published scenario.

Do not save raw `Turn N — user` messages, user prompts, planning or brainstorming, assistant meta-commentary, plot/cast metadata, turn wrappers, or an `End state` block. The user's supplied dialogue belongs in the scenario as in-scene dialogue when it has been incorporated there; do not duplicate the prompt that supplied it.

Keep the scenario full and novel-like. Preserve its location, narration, character dialogue, trackers, recap, and closing `Tumhari baari`/question when present. This storage rule changes only what is saved around the scenario; it does not shorten or otherwise change the story-writing pattern.

## Hard rule: explain unfamiliar terms for readers

When a new, invented, or potentially confusing worldbuilding term first appears in an act, add a brief plain-language explanation in square brackets immediately after it (for example, `ley-cell [a compact magical unit that stores leyline power for devices]`). Keep the explanation short and in the scenario; do not assume readers have read the worldbuilding files. Do not explain familiar terms repeatedly unless context requires it.

When editing existing files, preserve the scenario prose and in-scene dialogue. Remove only prompt/meta wrappers and redundant title headings. Do not invent actions, decisions, or dialogue for Love. Add or revise Love's in-scene words only when the author requests it. Do not date session filenames, headers, or bodies. Keep existing filenames unless the author asks to rename them.

## Template

```md
# Does the Dragon Princess Really Hate Me?
## Chapter 1 — Act 6: Ghar Ki Raah Aur Jungle Ka Pukaar

Location: Royal Healer Wing and Leyline Docks, Drakon Court

[Complete scenario: narration and dialogue]

## Rivona’s Feelings Tracker
[Tracker, when present]

## Haalat ka chhota sa recap
[Recap, when present]

## Tumhari baari, Love
[Closing prompt/question, when present]
```

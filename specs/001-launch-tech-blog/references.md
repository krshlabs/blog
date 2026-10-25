# Reference blogs

Living set used to judge how the blog looks and reads. Visitors do not see this list. Add an entry when a blog should inform a later design pass. Each note says what to learn, not what to copy.

## Exposing NSDictionary

- **Address**: https://ciechanow.ski/exposing-nsdictionary/
- **Author**: Bartosz Ciechanowski
- **Informs**: Article reading
- **Added**: 2026-10-25

What to learn from this page:

- The article is the page. Author and date are quiet; nothing beside the essay competes with it.
- The opening is a concrete fascination and a question, not a definition or an outline.
- Sections mark stages of an investigation. Headings are few and earned.
- Code and disassembly sit inside the argument as evidence. They are readable and visually quiet next to the prose.
- The close keeps one idea worth remembering and treats the exact internals as something that will go stale. Understanding outlives the snapshot.

This entry is the written essay. It does not, by itself, require interactive figures in the first release.

## Log-structured storage

- **Address**: https://jvns.ca/blog/2017/06/11/log-structured-storage/
- **Author**: Julia Evans
- **Informs**: How a topic is explained, and the tone of the language
- **Added**: 2026-10-25

What to learn from how this page explains the topic:

- It starts from a moment of learning ("this morning I read…") and a concept that was new, not from a formal definition.
- The mechanism arrives as the smallest thing that works: two short commands that append a line and read the latest one back. She says she tried it.
- The name of the idea comes after the reader has already watched it work.
- Nearby ideas that people mix up are separated in plain steps. A write-ahead log and log-structured storage get different jobs, each in a few sentences.
- Real systems (PostgreSQL, SQLite, Cassandra, and others) appear as landmarks after the toy version, so the abstraction has somewhere to land.
- A wrong earlier belief is corrected in the open, including why the usual word was misleading.
- A picture or a short quotation from a primary source shows up only after the intuition is already in place.

What to learn from the tone:

- First person, and still in the middle of understanding. The writer is a peer who got curious, not a lecturer who already finished.
- Spoken rhythm: short sentences, asides, and enthusiasm that stays specific ("I tried it", "losing data is bad").
- Hedges stay honest ("I think the deal is now") instead of pretending the last word is settled.
- Jargon is welcomed and then translated. Confusion about a word is treated as normal, including for the writer.
- The piece is allowed to end while still interested, once the new idea is usable.

## Integral of Sin(x): Geometric Intuition

- **Address**: https://betterexplained.com/articles/integral-sinx/
- **Author**: Kalid Azad, BetterExplained
- **Informs**: Math-based articles — visualization and step-by-step explanation
- **Added**: 2026-10-25

What to learn from the step-by-step explanation:

- The stock phrase is named first, then set aside, so the reader knows which "correct" answer is about to be replaced.
- Each symbol is translated on its own before the symbols are combined. Integral becomes accumulation, sine becomes a percentage, the tiny step becomes a short piece of a path.
- Those translations collapse into one plain sentence the reader can repeat.
- A frozen case comes before the changing case. If sine were always 75%, the result is obviously 75% of the path. Only then does the percentage start to move.
- Each section has one job and ends on a sentence that states the idea so far.
- The official formula arrives after the picture already predicts the number. The formula is a check, and the awkward negatives get an explanation.
- The shortcut (end minus start) is named only once the picture has made that shortcut visible.

What to learn from the visualization:

- The picture is the path being traveled. It shows up at the sentence that needs it, with a decoder key that names every mark.
- A tiny change is drawn as the same triangle, turned and scaled, so the new motion is the old one made small.
- A known interval can be read off the drawing before any calculation. From the start of the circle to the far side, the horizontal travel is two units, and the formula then returns 2.
- A short physical comparison holds one relationship and is not asked to carry the whole article.
- The familiar rectangle is a picture of multiplication. The article says when that picture stops being literal area.

This entry is one article, for math posts. The pictures it teaches are still diagrams inside the writing. Manipulable figures stay a later release.

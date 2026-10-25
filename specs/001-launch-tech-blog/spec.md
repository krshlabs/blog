# Feature Specification: Launch Technical Blog

**Feature Branch**: `001-launch-tech-blog`

**Created**: 2026-10-25

**Status**: Draft

**Input**: User description: "Create a blog at blog.krsh.io. Core focus is high-clarity technical blogging that prioritizes intuitive understanding over exact explication, covering systems-level engineering, architecture, code visualizers, and low-level mechanics. Start with a simple, zero-overhead written blog today, and keep published articles ready to gain interactive figures later without rewriting them or changing their public addresses. Keep a living set of inspired blogs so the design can be refined over time, starting with https://ciechanow.ski/exposing-nsdictionary/ and also https://jvns.ca/blog/2017/06/11/log-structured-storage/ for how it explains the topic and the tone of the language. For math-based articles, use https://betterexplained.com/articles/integral-sinx/ for how it uses visualization and step-by-step explanation."

## User Scenarios & Testing *(mandatory)*

### User Story 1 - Read a technical article (Priority: P1)

A reader opens a published article and follows a written explanation of a systems, architecture, or low-level topic from the core idea through to the mechanics. Formatted code examples stay readable. The article is complete as writing; the reader does not need extra software or an account.

**Why this priority**: Reading a finished article is the reason the blog exists. A single published article is a viable first release.

**Independent Test**: Publish one article and open it in a browser. Confirm the title, date, opening idea, full explanation, and any code examples are readable on a phone and on a desktop.

**Acceptance Scenarios**:

1. **Given** a published article, **When** a reader opens its public address, **Then** they see the title, publication date, and full written body.
2. **Given** a published article, **When** a reader starts at the top, **Then** they encounter a plain-language statement of the idea before the detailed mechanics.
3. **Given** an article that includes a code example, **When** a reader views it on a narrow screen, **Then** the page itself does not scroll sideways and the code example remains readable within its own area.
4. **Given** a published article, **When** a reader has no account, **Then** they can still read the entire article.
5. **Given** a math article with a still diagram at the step it explains, **When** a reader reaches that step, **Then** the diagram is part of the written page and can be read there without a separate interactive view.

---

### User Story 2 - Discover what to read (Priority: P2)

A visitor arrives at the blog and sees which articles are available, newest first, with enough information to choose one and open it.

**Why this priority**: A blog with more than one article needs a front door. This story is independently useful once at least one article exists, and it is what makes a second article findable.

**Independent Test**: Publish two articles on different dates. Open the home page and confirm both appear, newest first, and each opens the correct article.

**Acceptance Scenarios**:

1. **Given** one or more published articles, **When** a visitor opens the blog home, **Then** they see each article's title, publication date, and a short summary, ordered newest first.
2. **Given** the home page, **When** a visitor chooses an article, **Then** they reach its full text in one step.
3. **Given** no published articles, **When** a visitor opens the home page, **Then** they see a clear explanation that there is nothing to read yet, not an error.

---

### User Story 3 - Return to the same article (Priority: P3)

A reader or the author shares an article's public address. Anyone who opens that address later gets the same article, including after the author edits the text.

**Why this priority**: Technical posts are cited and re-read. A stable address is what makes a post a reference rather than a one-time page.

**Independent Test**: Publish an article, record its address, edit the body, and open the same address again. Confirm the updated text appears and the address did not change.

**Acceptance Scenarios**:

1. **Given** a published article, **When** the author edits its text and publishes the update, **Then** the public address is unchanged and visitors see the updated text.
2. **Given** a shared public address, **When** another person opens it, **Then** they see that article without any extra navigation.
3. **Given** two finished articles, **When** the author publishes both, **Then** each receives its own public address and neither overwrites the other.
4. **Given** an already published article, **When** an interactive figure is later added beside the writing, **Then** the public address and the existing written explanation stay the same.

---

### User Story 4 - Publish a finished article (Priority: P4)

The author finishes a written article and publishes it. It then appears on the home page and at its own public address. Work that is not ready stays invisible to visitors.

**Why this priority**: The author must be able to add posts without a separate product. Drafts must not leak. This can be tested with a single article and does not depend on discovery beyond that article's address.

**Independent Test**: Prepare one finished article and one unfinished draft. Publish only the finished article. Confirm only the finished article is publicly visible.

**Acceptance Scenarios**:

1. **Given** a finished article with a title, publication date, summary, and body, **When** the author publishes it, **Then** it appears on the home page and at its public address.
2. **Given** an unfinished draft, **When** a visitor opens the home page or guesses an address, **Then** the draft is not shown.
3. **Given** an article missing a title, publication date, or body, **When** the author attempts to publish it, **Then** it is not published and the gap is apparent to the author.
4. **Given** a published article, **When** the author unpublishes it, **Then** it disappears from the home page and its public address no longer serves it to visitors.

---

### User Story 5 - See who is writing and what the blog is for (Priority: P5)

A new reader can tell who writes the blog and that it explains systems, architecture, and low-level mechanics in a way that favors intuition first.

**Why this priority**: The point of view is part of the product, but a reader can still finish an article without it. It is a thin companion to the reading experience.

**Independent Test**: Open the blog with no prior context and find the author's name and a short description of what the blog covers, without opening an article.

**Acceptance Scenarios**:

1. **Given** a first-time visitor, **When** they look at the home page, **Then** they can read the author's name and a short description of the blog's focus.
2. **Given** that description, **When** a visitor reads it, **Then** it states that explanations favor intuitive understanding of systems, architecture, and low-level mechanics.

---

### User Story 6 - Refine the design against reference blogs (Priority: P6)

The author keeps a living set of blogs and articles that the reading experience should learn from. The set starts with one article and can grow as the design is refined. Readers do not see this set. Adding a reference does not change anything already published.

**Why this priority**: The first release can be read without this list, but design decisions should not be made from memory. The set is how later visual refinements stay anchored.

**Independent Test**: Open the reference set, confirm the first entry is present with a note on what to learn from it, add a second entry, and confirm published articles are unchanged.

**Acceptance Scenarios**:

1. **Given** the reference set, **When** the author consults it, **Then** it includes [Exposing NSDictionary](https://ciechanow.ski/exposing-nsdictionary/), [Log-structured storage](https://jvns.ca/blog/2017/06/11/log-structured-storage/), and [Integral of Sin(x): Geometric Intuition](https://betterexplained.com/articles/integral-sinx/), each with a short note on what to learn. The Evans note covers explanation and tone. The BetterExplained note covers visualization and step-by-step explanation for math-based articles.
2. **Given** the current set, **When** the author adds another blog or article, **Then** the new entry is kept beside the existing ones and no published article changes.
3. **Given** a proposed change to how articles are presented, **When** that change is reviewed, **Then** it is compared against the references currently in the set.

---

### Edge Cases

- No articles have been published yet: the home page still loads and explains the empty state.
- A draft is the only article that exists: visitors see the empty state, not the draft.
- Two articles would claim the same public address: the later one is not published until it has a distinct address.
- An article is updated after people have already shared it: the shared address still opens it and shows the latest published text.
- An article is unpublished after it was shared: visitors no longer receive the article at that address.
- An article is very long: headings remain available in the text and the page stays readable from start to finish.
- A code example is wider than the screen: the reader can scroll inside the example; the rest of the page does not shift sideways.
- An article has no short summary: it cannot be published until a summary exists, so the home page never lists a blank entry.
- A later interactive figure is added to an already published article: the written body and public address stay intact, and the figure is an addition rather than a replacement.
- A reference page later becomes unavailable: the set still records what was worth learning from it, and the public blog is unaffected.
- The author adds a reference that inspires a different quality than the first (for example, a home page rather than an article): both stay in the set, and each note says which part of the blog it informs.

## Requirements *(mandatory)*

### Functional Requirements

- **FR-001**: The blog MUST be publicly readable at blog.krsh.io with no visitor account.
- **FR-002**: Each published article MUST show its title, publication date, and full written body.
- **FR-003**: Each published article MUST open with a plain-language statement of the idea before detailed mechanics.
- **FR-004**: Articles MUST be able to include formatted code examples that stay readable on a narrow screen without making the rest of the page scroll sideways.
- **FR-005**: The home page MUST list every published article, newest first, showing title, publication date, and a short summary.
- **FR-006**: A visitor MUST be able to open a full article from the home page in one step.
- **FR-007**: Each published article MUST have one stable public address under blog.krsh.io.
- **FR-008**: Editing a published article MUST keep its public address and show the updated text to later visitors.
- **FR-009**: The author MUST be able to publish a finished written article so it appears on the home page and at its public address.
- **FR-010**: An article MUST NOT be publishable unless it has a title, publication date, short summary, and body.
- **FR-011**: Two published articles MUST NOT share the same public address.
- **FR-012**: Unpublished drafts MUST NOT appear on the home page and MUST NOT be served at a public address.
- **FR-013**: Unpublishing an article MUST remove it from the home page and stop serving it at its public address.
- **FR-014**: When nothing is published, the home page MUST explain that there is nothing to read yet instead of showing an error.
- **FR-015**: Article prose MUST be readable on a phone and on a desktop without horizontal scrolling of the page.
- **FR-016**: The home page MUST show the author's name and a short description of the blog's focus: intuitive explanations of systems-level engineering, architecture, and low-level mechanics.
- **FR-017**: The first release MUST treat every article as complete written explanation. Interactive figures are not part of this release.
- **FR-018**: A published article MUST keep its public address and its written body when an interactive figure is later added beside that writing. The figure MUST NOT require a new address or a rewrite of the existing explanation.
- **FR-019**: The project MUST keep a reference set of inspired blogs and articles used to judge changes to how the blog looks and reads.
- **FR-020**: The reference set MUST include `https://ciechanow.ski/exposing-nsdictionary/`, `https://jvns.ca/blog/2017/06/11/log-structured-storage/`, and `https://betterexplained.com/articles/integral-sinx/`, each with a short note on what to learn. The Evans note MUST cover how that post explains the topic and the tone of its language. The BetterExplained note MUST cover visualization and step-by-step explanation, and it applies when an article is math-based.
- **FR-021**: The author MUST be able to add, annotate, or remove reference entries over time. Doing so MUST NOT change published articles or their public addresses.
- **FR-022**: A change to how articles or the home page are presented MUST be reviewed against the reference set as it stands at that time.
- **FR-023**: The reference set MUST NOT be shown to visitors in this release.
- **FR-024**: A written article MUST be able to include still diagrams at the step they explain. Those diagrams are part of the written body. This release does not require them to be manipulable.

### Key Entities

- **Article**: A single technical explanation. Attributes: title, publication date, short summary, written body, public address, and publication status (draft or published). The body may later sit beside an interactive figure; the figure does not replace the writing or the address.
- **Author**: The single person responsible for the blog. Attributes: name and a short description of perspective and topics.
- **Blog**: The public site. Attributes: public address (blog.krsh.io), name, and the focus description visitors see before they choose an article.
- **Reference**: One inspired blog or article kept for design and editorial judgment. Attributes: address, what to learn from it, and which part of this blog it informs (article reading, math-based articles, home page, or a combination). The maintained list is [references.md](references.md). It is not part of the public site. Current entries: [Exposing NSDictionary](https://ciechanow.ski/exposing-nsdictionary/) by Bartosz Ciechanowski (the article is the page; a question, then code as evidence, then one idea that outlives the exact internals), [Log-structured storage](https://jvns.ca/blog/2017/06/11/log-structured-storage/) by Julia Evans (explain from a tiny working example and a misconception corrected in the open; tone is a peer still learning, specific, and spoken), and [Integral of Sin(x): Geometric Intuition](https://betterexplained.com/articles/integral-sinx/) by Kalid Azad (for math articles: decode one symbol at a time, then a still picture of the path with a decoder key, then the official formula as a check).

## Success Criteria *(mandatory)*

### Measurable Outcomes

- **SC-001**: A visitor can open the home page and reach the full text of a chosen published article in two steps or fewer.
- **SC-002**: On both a phone-width and a desktop-width display, a reader can move through an article's prose from title to ending without the page scrolling sideways.
- **SC-003**: The author can take a finished article (title, date, summary, and body already written) to a live public page in under 15 minutes.
- **SC-004**: After an article is edited, 100% of previously shared addresses for that article still open it and show the latest published text.
- **SC-005**: 100% of published articles state the core idea in plain language before detailed mechanics.
- **SC-006**: With zero published articles, a visitor still gets a coherent home page rather than an error.
- **SC-007**: In a review of the public site, zero draft articles are visible on the home page or at a public address.
- **SC-008**: Adding a later interactive figure to an existing article leaves that article's public address and written explanation unchanged.
- **SC-009**: The reference set includes the Ciechanowski article, the Julia Evans article, and the BetterExplained article, each with a note on what to learn. The Evans note covers explanation and tone. The BetterExplained note covers visualization and step-by-step explanation for math articles. Adding a further reference is one edit, and no published article changes because of that addition.

## Assumptions

- There is one author, the owner of krsh.io. Reader accounts, comments, subscriptions, and multiple authors are out of scope.
- The language of the blog is English.
- The public address readers and shared links use is blog.krsh.io. How the name is connected to hosting is already available to the author and is not part of this feature's behavior.
- Discovery in the first release is the reverse-chronological home list. Topic groupings, full-text search, and syndication feeds are out of scope until a later release.
- Interactive figures (something a reader can manipulate to see how a system or piece of code behaves) are a later release. This release only has to leave each published article's address and written body intact so those figures can be added beside the writing.
- The author prepares articles as written documents that stay separate from how the site presents them, so presentation can grow later without rewriting published explanations.
- A "short summary" is a few sentences the author writes for the home page, not an automatic excerpt that might start mid-thought.
- Code examples are part of the written article. A math article may also include still diagrams at the step they explain. Downloadable project files, runnable sandboxes, and manipulable visualizers are out of scope for this release.
- The editorial standard is intuitive understanding first: an article should let a reader grasp the idea before it tightens into exact mechanics. Exact reference documentation is not the goal of a post.
- The reference set is a project working list for design refinement. Visitors do not get an "inspiration" page in this release.
- Each reference is one page unless the note says otherwise. The Ciechanowski entry is that article, not the whole of ciechanow.ski. The Evans entry is that post, not the whole of jvns.ca, and it is there for explanation and tone. The BetterExplained entry is that article, not the whole of betterexplained.com, and it is there for math-based articles: visualization and step-by-step explanation. Later entries can point at a whole site, a home page, or another article, and each entry names the quality it is there to teach.
- This release does not copy that article's interactive figures. The written reading experience is what the first reference is for; manipulable figures remain a later release.

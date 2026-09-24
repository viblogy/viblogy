# viblogy

[中文](README.zh.md) | **English**

> Squeeze every last bit of value out of your AI collaboration sessions.

viblogy is a macOS desktop app for vibe-coding users. It centrally manages AI collaboration sessions exported in four formats — **Kimi / Qwen Code / Trae / Qoder** (manual import or watched folders) — plus a real-time monitoring pipeline for **Kimi / Qwen / Qoder / Codex** (Codex is experimental and off by default; only Trae has no real-time support). **It turns scattered AI conversations into readable progress reports, reviewable debugging lessons, and a traceable code map.**

> The app UI is currently Chinese-only; setting labels below are quoted in Chinese so you can find them in the app.

## It solves four problems

### 1. After a hundred-turn session, what did I actually finish?

Vibe-coding sessions easily run to hundreds of turns, and scrolling back through logs to recover progress is nearly impossible. viblogy turns "reading logs" into "reading conclusions":

- **Narrative AI summaries**: generates a four-part narrative from full turn-by-turn understanding — Background & Goals / Process / Key Decisions & Turning Points / Final Outcome; ultra-long sessions are summarized in layers, and failed runs resume from checkpoints.
- **Turn understanding**: every turn gets a structured Markdown write-up (goal / process / significance + outcome checklist), carrying the previous turn's understanding as chained context, so the evolution of your thinking is traceable turn by turn.
- **Decision records**: after each turn's understanding, **decision cards** are distilled automatically — problem / solution / constraints / rationale / outcome, one card per decision. Mark key ones as important, dismiss noise (restorable anytime); cards are searchable too, so "why did we decide this?" no longer means digging through raw logs. Historical sessions can be backfilled, with resume after interruption.
- **DevPlan checklists**: import a development plan document to generate a structured task list; turn understanding automatically judges task progress. A progress banner at the top of the timeline shows where things stand, and clicking a task jumps back to the related conversations.
- **Search & Q&A**: keyword search with project/time filters goes straight to the source text; session-level AI Q&A answers "why was this changed back then" against the full session context, with `@turn` references and one-click conversion of answers into notes.

### 2. After dozens of debugging rounds, where did it actually go wrong?

Futile multi-round debugging loops are vibe-coding's biggest hidden cost. viblogy helps you break the loop and review the whole journey:

- **Debug retrospectives**: three-stage analysis (intent & role analysis → cross-turn clustering → deep retrospective) producing root cause / troubleshooting process / strategy assessment / lessons learned, with key-path jumps and export. Conclusions anchor to concrete files — AI identifies the root-cause file, jumpable in the code tree, with snapshots of affected files. You can restrict analysis to turns that actually worked on the error — faster and cheaper.
- **"Known limitations & unverified claims" in handoff documents**: when generating a handoff document, viblogy collects the trade-offs **explicitly accepted** and the **code-behavior claims stated without verification evidence** in the session, each annotated with its source turn — whoever takes over won't mistake "unwritten risks" for "no risks". Without an AI service configured it degrades to a raw signal list; the feature never breaks.
- **Session-level AI Q&A**: ask directly "in which turn did this bug first appear" or "how many times has this class of issue been fixed" — answers draw on the full context without missing early clues.

### 3. AI-written code is a black box — how do I take responsibility for it?

You can't vouch for the safety or quality of code you can't read. viblogy makes the black box transparent with local analysis plus AI annotations:

- **Project code tree**: after you confirm the project root, it scans the real filesystem (respecting `.gitignore`), with recursive lazy loading and historical markers for deleted files; four categories (docs / tests / lockfiles / static assets) can be excluded from the tree.
- **AI node annotations**: one click generates a 1–3 sentence plain-language annotation for any file or directory — what this file stores and what it builds; multi-select a scope for batch annotation, with upfront estimates and resumable runs, keeping token costs under control.
- **Impact linking & tracing**: file paths mentioned in conversations are automatically linked to code-tree nodes; tree nodes show impact badges, and the tracing panel lists "which conversation changed which file" with evidence excerpts and one-click jumps back to the exact timeline turn.
- **Uncommitted changes overview**: a read-only view of uncommitted git changes, grouped by worktree/session, with optional AI summarization; branch status and recent commits at a glance.
- **Data-flow flowcharts & interpretation**: a three-layer upstream/downstream graph over the tree area with AI-annotated data semantics on edges; click a node to refocus and drill down layer by layer. Pick any two nodes and AI explains how data flows between them — and which conversation created that path.
- **Graph export & path copying**: export the currently visible graph to Markdown in one click (three optional sections: node annotations / meso descriptions / path explanations). Missing or stale content is listed all at once — choose "fill in and continue" or "export as-is" without item-by-item interruptions; whether to regenerate stale content is your per-item choice, with costs made explicit. Node cards also copy the file's absolute path in one click.

### 4. A new idea is ready to start — how do I hand the context to AI in one shot?

A fresh session starts from zero: the AI has to search the whole repo to bootstrap itself — slow and prone to misses. viblogy lets you pack up the project knowledge you've already accumulated and take it with you:

- **Project milestones**: import a development plan document and AI organizes it into a cross-session checklist; repeated imports merge and deduplicate, entries can be edited manually, drag-sorted, and grouped (AI re-organization can process only ungrouped entries, with a group-count cap). Every entry is an idea waiting to start.
- **Context packages**: click the package button on an entry and viblogy assembles a Markdown context — requirements with keywords you've confirmed / relevant code facts / similar past sessions / related files / where project conventions live / pitfall warnings — every section expandable to see the evidence behind "why this matched". **Assembly makes no AI calls**: with no AI service configured you can still assemble, preview, and copy, all in seconds.
- **Honest coverage reporting**: the package states which sections matched and which are empty — empty sections say "no hits" instead of inventing fake matches. The coverage percentage tells you how ready this idea is to start. After a codebase rescan, packages are marked stale automatically; one click re-assembles, and the document header always states the as-of time — never silently serving stale facts.
- **Package a whole group at once**: the package button on a group header combines **every entry in the group** into one package. Files hit by multiple entries go into a "shared within group" block labeled with their source entries — several pointers to the same file means a shared dependency you should know about before touching it. You can temporarily exclude entries before assembly (recomputed instantly, affecting only this package, not the grouping itself), with one-click restore; coverage reports each entry's status alongside the group total, so aggregate numbers never mask underprepared entries.
- **Pitfall warnings**: the package collects pitfalls this project has actually hit — failed operations, changes made from stale content, and trade-offs or unverified claims recorded in past sessions — so the next person doesn't step on them again.
- **Delivery with a paper trail**: copying or exporting `.md` counts as a delivery and updates entry status (toggleable); sections you delete in the preview are remembered, and the document header honestly states which sections were removed — recipients won't misread "no pitfall warnings" as "this project has no pitfalls".
- **Export & handoff center**: sessions themselves export in one click — the "Handoff document" preset targets the next AI taking over (ten structured handoff sections plus a session summary), while "Session archive" targets your own records (original text + understanding + summaries + impact links, in seconds). Turn range and content mix are two independent axes, with a collapsible live preview on the right; key-like sensitive content is filtered automatically, and the filtering policy is declared in the document header.

## System requirements

- macOS 12 or later
- Currently available for **Apple Silicon (M-series chips)**
- 8 GB RAM or more recommended (16 GB is better for AI features and large sessions)

## Download & installation

1. Visit the [Releases](https://github.com/viblogy/viblogy/releases) page and download the latest `.dmg` file;
2. Open the `.dmg` and drag **Viblogy** into the Applications folder;
3. The app is Developer ID signed and Apple notarized, so it normally opens directly; if Gatekeeper still prompts, go to System Settings → Privacy & Security and choose "Open Anyway";
4. First install comes with a **30-day full-featured free trial**, no account registration required (trial and licensing terms in the [EULA](EULA.md)).

## Quick start

1. **Import your first session**: export a session as `.md` from Kimi / Qwen Code / Trae / Qoder and drag it onto the timeline (format auto-detected, no manual selection). Or enable real-time session monitoring in 「设置 → 导入与监测」 — four independent toggles for Kimi / Qwen / Qoder / Codex (Codex is experimental and off by default; only text visible to you and the assistant is captured). New conversations then sync automatically, no manual export needed.
2. **Link a project and browse the code tree**: create a project in the sidebar, enter the project view, and confirm the code root to browse the code tree, AI annotations, and impact tracing. Frequently used projects can be pinned — a pinned project is selected by default at launch.
3. **Configure an AI service**: go to 「设置 → AI 服务」, add a configuration, and test the connection (quick-fill from multiple provider presets, or custom endpoints and headers); summaries, understanding, Q&A, and other AI features all go through your own configured endpoints — token costs are yours to control. Context-package assembly does not require an AI service.
4. **Package context for the next idea**: in the project view's 「里程碑」 tab, jot down ideas (candidate-word suggestions appear as you type — clicking one never rewrites what you've entered), click the package button on an entry to assemble its context, then copy or export `.md` as a first-prompt attachment for a new session.
5. **Back up regularly**: go to 「设置 → 数据备份」 and export a zip backup (database, session contents, and notes) in one click.

## License

viblogy is closed-source proprietary software; copying, distribution, or modification without permission is prohibited. See the [End User License Agreement (EULA)](EULA.md) for rights, trial, and licensing terms, and the [Privacy Policy](PRIVACY-POLICY.md) for data handling. Both legal documents are currently available in Chinese only. The current version is a beta release; see EULA Section 4 for the special terms that apply.

© 2026 viblogy. All rights reserved.

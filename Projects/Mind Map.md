Mind Map\*\* is a local-first, AI-assisted note-taking and knowledge management desktop application built with **Tauri v2** (Rust), **Vue 3**, and **TypeScript**. It stores documents as Markdown files in a local git repository, with SQLite for metadata.

### Features

1. **Document Management** — Create, edit, delete, rename Markdown documents with WYSIWYG editing (Milkdown), nested folder tree, drag-and-drop, favorites/pinning, auto-save with debounced git auto-commits.

2. **Folder & Tag Organization** — Unlimited-depth nested folders, multi-tag support, AI auto-tagging on save, manual tag CRUD, tag filtering, color-coded tags.

3. **AI Chat Panel** — Docked chat alongside editor with streaming responses, markdown rendering, context-aware (reads current doc or selection), quick actions (summarize, expand, rephrase, brainstorm, find links), copy-to-document.

4. **AI Provider Abstraction** — Pluggable providers: Ollama (default), LM Studio, OpenAI-compatible APIs. Configurable base URL, API key, model, health check, fallback support.

5. **Knowledge Graph** — Interactive visual graph of document relationships, manual + AI-suggested links, force-directed layout with clustering, zoom/pan/search, mini-map.

6. **Full-Text & Semantic Search** — Search-as-you-type across titles/content, filter by folder/tag/date, AI-powered semantic search via embeddings, "Ask AI" mode for natural-language Q\&A grounded in documents (RAG).

7. **Git Sync** — Auto-init repo on first launch, auto-commit on save, manual push/pull to remote (GitHub/GitLab/self-hosted), periodic auto-sync, history viewer with diffs, revert to any commit, merge conflict resolution UI, status indicator.

<br />

##

<br />

1. **Version Control Viewer** — Browse commit log, view per-document diffs, restore previous versions.

2. **Export** — Export documents to Markdown, HTML, PDF.

3. **Settings** — AI provider config, light/dark mode, font size, editor theme, data path override, git remote config, language/locale, import/export settings.

4. **Security & Privacy** — 100% local-first, no telemetry, API keys in OS keychain, optional biometric lock, git credentials in keychain, user-controlled sync.

* [ ] Select and restore version

* [ ] AI summarize grammar check

* [ ] Undo redo system

* [ ] Compress commit and limit the version to be saved

  <br />

  <br />

  <br />

  <br />

  <br />

  <br />

  <br />

  <br />

  <br />

  <br />

  <br />

  <br />


### Features

1. **Document Management** — Create, edit, delete, rename Markdown documents with WYSIWYG editing (Milkdown), nested folder tree, drag-and-drop, favorites/pinning, auto-save with debounced git auto-commits.

2. **Folder & Tag Organization** — Unlimited-depth nested folders, multi-tag support, AI auto-tagging on save, manual tag CRUD, tag filtering, color-coded tags.

3. **AI Chat Panel** — Docked chat alongside editor with streaming responses, markdown rendering, context-aware (reads current doc or selection), quick actions (summarize, expand, rephrase, brainstorm, find links), copy-to-document.

4. **AI Provider Abstraction** — Pluggable providers: Ollama (default), LM Studio, OpenAI-compatible APIs. Configurable base URL, API key, model, health check, fallback support.

5. **Knowledge Graph** — Interactive visual graph of document relationships, manual + AI-suggested links, force-directed layout with clustering, zoom/pan/search, mini-map.

6. **Full-Text & Semantic Search** — Search-as-you-type across titles/content, filter by folder/tag/date, AI-powered semantic search via embeddings, "Ask AI" mode for natural-language Q\&A grounded in documents (RAG).

7. **Git Sync** — Auto-init repo on first launch, auto-commit on save, manual push/pull to remote (GitHub/GitLab/self-hosted), periodic auto-sync, history viewer with diffs, revert to any commit, merge conflict resolution UI, status indicator.

8. **Version Control Viewer** — Browse commit log, view per-document diffs, restore previous versions.

9. **Settings** — AI provider config, light/dark mode, font size, editor theme, data path override, git remote config, language/locale, import/export settings.

10. **Security & Privacy** — 100% local-first, no telemetry, API keys in OS keychain, optional biometric lock, git credentials in keychain, user-controlled sync.

# Todo

* [ ] **Select and restore version**
  * Implement a UI component allowing users to view the commit history of a document.

  * Provide options to select a specific commit or tag.

  * Restore the selected version back into the current working document, ensuring data consistency and handling any necessary merge conflicts.

* [ ] **AI summarize grammar check**
  * Integrate an AI model capable of performing grammar checking on user-generated text within documents.

  * Offer real-time suggestions for grammatical improvements directly in the editor.

  * Summarize highlighted sections to provide concise feedback on writing quality.

* [ ] **Undo/redo system**
  * Develop a robust undo and redo stack that captures state changes at both the document and editing level (e.g., text insertion, deletion, formatting).

  * Ensure atomicity for complex operations like auto-commits in git sync to maintain logical consistency.

  * Provide user-friendly controls (keyboard shortcuts and UI buttons) for navigating through history.

* [ ] **Compress commit and limit the version to be saved**
  * Implement a mechanism to detect and merge similar commits automatically, reducing redundancy in the commit history.

  * Define criteria or thresholds for what constitutes "similar" commits based on content changes or timestamps.

  * Allow users to configure limits on the number of stored versions per document, prompting archiving or deletion when exceeded.


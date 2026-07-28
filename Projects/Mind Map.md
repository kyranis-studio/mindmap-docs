### Mind Map — Agent Guide

## Stack

* **Desktop shell:** Tauri v2 (Rust). Entrypoint: `src-tauri/src/main.rs` → `mind_map_lib::run()` in `lib.rs`

* **Frontend:** Vue 3 + TypeScript, Vite. Entrypoint: `src/main.ts` → `src/App.vue`

* **Package mgmt:** npm deps via Deno (`deno.lock`), but no `deno.json` committed — use `npx`/`npm` directly. `deno install` to sync lockfile if present.

* **Rust deps:** Cargo (`src-tauri/Cargo.toml`)

## Dev Commands

* `npx tauri dev` — desktop dev (Vite on port **1420**, strict; Vite ignores `src-tauri/`)

* `npm run build` — typecheck (`vue-tsc --noEmit`) + `vite build`

* `npm run preview` — Vite preview

* `npm run tauri -- <args>` — Tauri CLI passthrough

No linter, formatter, or test framework is configured.

## Architecture

### Data Storage

* Documents: flat `.md` files (or `.emd` for encrypted) in the workspace directory

* Metadata: `workspace/.mindmap/metadata.json` (favorites, tags, passwords, positions, dates)

* RAG index: `workspace/.mindmap/vectors/index.json`

* No SQLite yet (PRD specifies it, not implemented)

* Workspace path stored in `localStorage` key `mindmap-workspace`

* Model settings in localStorage keys: `mindmap-chat-model`, `mindmap-embedding-model`, `mindmap-editing-model`, `mindmap-vision-model`

* System prompts in localStorage: `mindmap-chat-system-prompt`, `mindmap-editing-system-prompt`, `mindmap-vision-system-prompt`

* Chat sessions stored in localStorage key `mindmap-chat-sessions` (capped at 50 sessions, 200 messages each)

* Credentials stored in `mindmap-git-credentials`

### Auto-save

* Document content: 800ms debounce (`scheduleSave`)

* Metadata JSON: 500ms debounce (`scheduleMetadataSave`)

### AI (Rust backend, hardcoded to `localhost:11434`)

* Ollama required for embeddings & chat. Default models: `llama3.2` (chat), `nomic-embed-text` (embeddings), `llava` (vision)

* RAG commands: `rag_index_workspace`, `rag_query`, `rag_query_stream` (auto-indexes if no index exists), `cancel_rag_query`

* Streaming events: `rag:token`, `rag:done`, `edit:token`, `edit:done` (Tauri events)

* Editing via AI: `edit_with_ai_stream` — returns only edited content, no commentary

* Document chat: `chat_with_doc_stream` — per-document Q&A (emits `rag:token`/`rag:done`)

### Encryption

* AES-256-GCM with PBKDF2 (100k iterations)

* Encrypted files use `.emd` extension; SHA-256 password hash stored in metadata

* Password hashing client-side in `src/utils/hash.ts` (Web Crypto `crypto.subtle.digest`)

### Git (Rust backend, shells out to `git` CLI)

* Commands: `git_init`, `git_clone`, `git_sync`, `git_status`, `git_diff_file`, `git_checkout_file`, etc.

* Auto-sync: `git add -A` + `git commit -m "Auto-sync"` + pull (`--no-rebase -X theirs -X ignore-all-space`) + push

* Workspace polling: `git status` every 3s, remote check every 30s

### Notable Conventions

* CSP is disabled (`"csp": null` in `tauri.conf.json`)

* `diff=ignoreall` in `.gitattributes` for all source files

* CRUD logic lives entirely in `src/App.vue` (\~2821 lines, not in Pinia stores)

* Component count: 16 components in `src/components/`

* No routing (single-window app, `activeView` toggle)

* Mock data in `src/store/mockData.ts` for dev without backend

<br />

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


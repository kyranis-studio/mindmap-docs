### Mind Map — Agent Guide

Update the auto save strategy 

* commit all  change locally 
* combine all multiple local commit for shorter history
* synchronize only on app load 

<br />

* remove all synch button the synch will be executed automatically

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

  * <br />


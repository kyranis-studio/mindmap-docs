<br />

* [ ] update to vite 8 => 87% faster

* [ ] add the Voter in the leave V3 page

* [ ] devkit add documentation pull in the devkit build environment

* [ ] devkit add github feature with llm integration

* [ ] devkit smart build using git

* [ ] update the vite build with chunking strategies.

* [ ] fix build warning

* [ ] HMR rebuild only modified file

* [ ] rebase the project using laravel

* [ ] dark mode fix TDS cell table

What was set up
Path Branch Docs tracked?
Code (main checkout) /home/devfactory/Projects/olafatco release/2.23/leave\_V3 ❌ ignored (unchanged)
Notes (worktree) /home/devfactory/Projects/olafatco-notes docs/ai-migration ✅ committed
Verification:

git ls-files "AI migration" on the feature branch → empty (not tracked).
The docs commit 9796a3d8e6 is not an ancestor of release/2.23/leave\_V3 → merging the feature branch into develop/master can never bring the docs along.
git worktree list shows both checkouts; your code working tree is untouched (still at a5458303b4).
On the notes branch I also removed the /AI migration/ line from its .gitignore (the code branch keeps it), so the folder is a normal tracked folder there. The 7 docs are committed as one commit.

How to use it day-to-day

# edit / view the notes (they are the tracked copy)

cd /home/devfactory/Projects/olafatco-notes
\$EDITOR "AI migration/TEST\_STRATEGY.md"
git add -A && git commit -m "docs(ai-migration): ..."

# confirm the layout any time

git -C /home/devfactory/Projects/olafatco worktree list
When you're done with it entirely:

git -C /home/devfactory/Projects/olafatco worktree remove /home/devfactory/Projects/olafatco-notes
git -C /home/devfactory/Projects/olafatco branch -D docs/ai-migration # optional
Pushing docs/ai-migration to origin is fine (it's a normal branch) and still won't merge itself.

One thing to be aware of
Your main checkout still has the earlier untracked, ignored copy at /home/devfactory/Projects/olafatco/AI migration/. It can't be committed on the feature branch, but it's now a stale duplicate — if you keep editing that one, your changes won't be versioned. Recommended: edit the worktree copy from now on.

Want me to delete the stale copy in the main checkout so there's a single source of truth? I can also, going forward, apply any doc edits I make directly in the worktree (/home/devfactory/Projects/olafatco-notes/AI migration/).


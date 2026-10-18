###### bug fix

* [ ] fix the context metrics the chat gey the right context but the context % don't update correctly

* [ ] none

###### Priority

* [ ] add memory management

* [ ] update the tool for local llm

- [ ] Add diff collapseable

- [ ] add an UI tool node

- [ ] Queue message

- [ ] add a browser tab for agent to debug

- [ ] memory strategy node (full context/summarize)

- [ ] AI model control the IDE

- [ ] add and update server

- [ ] MCP server/client

- [ ] in the knowledge code structure show non-treated files with tree sitter

- [ ] Use AI for non-processed files to generate graph knowledge

- [ ] none

###### Features

* [ ] **node graph time laps**

* [ ] UI designer tab

* [ ] add llm routing (choose the best llm to use)

- [ ] add git tab

* [ ] add tools permission

* [ ] add database in knowledge tab

* [ ] add a browser tab

* [ ] add memory for actions

###### Prompts

In the status bar, I have multiple metrics: chat token/second context % "assisting generating."

Remove the "assisting generating."

The chat holds how much token is generated

The context must hold the token of all the sessions. But it keeps resetting after a new message

Remove the chat; use only the context. Show the full context of the context used and its %

The context must be used to trigger the context compression. Make sure to wire the value to the feature

check all the tools and implement the best strategy of execution optimize for local LLM

the badge live in the collapsible is in every collapsible; make sure it is only in the current generation just the last collapsible must have live when there is a generation

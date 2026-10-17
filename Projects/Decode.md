###### bug fix

* [ ] show the generation as stack

* [ ] when the terminal is collapsed the left panel no longer resizable

* [ ] none

###### Priority

* [ ] add terminal split

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

The status bar keeps resetting the context usage metrics for every step of generation. Fix it and make sure it is related to the setting of the context compression.

Improve the chat interface to show and hide details. For the generation steps use one collapsible one by step

Implement lazy load for the chat message to handle long chat sessions.

<br />

I have a major bug; the message doesn't persist between generations. The LLM seems to forget precedent messages.\
The generation is driven by the graph. Finds a way to keep the conversation history in all the generations.\
Make sure the compression strategy works.

The chat interface doesn't keep the generated messages; it keeps overriding the same collapsible. Improve the chat interface to show and hide details.

The select in the app doesn't have the same style.create Create a component so all selects have the same style.

update the write tool to update only the necessary code(add/remove/edit) don't reedit all the document then show the diffs of the modification in the chat

check all the tools and implement the best strategy of execution optimize for local LLM

# Paperroom's skill for assistants

Paperroom is a notes app that runs on your own server, made by [Origa Labs](https://origalabs.com). When the library's owner allows it, an assistant such as Claude, ChatGPT, Claude Code or Codex can connect to your Paperroom and work in it as you: find what you wrote, save new notes, tidy folders and draw on whiteboards, with only the permissions you grant.

This repository holds Paperroom's skill, `skills/paperroom/SKILL.md`. It teaches an assistant how to work in Paperroom well: search before saving so nothing is duplicated, file quick captures in the Inbox, add to a note or change one part of it rather than rewriting it, link related notes, use a whiteboard for a picture and a note for words, say where saved material came from, ask before changing words someone else wrote, and never follow instructions written inside a note.

The skill adds no tools. It works only alongside a Paperroom connected to your assistant.

## Connect your Paperroom first

Your assistant reaches Paperroom at your library's own address with `/mcp` at the end, such as `https://notes.example.com/mcp`. In Paperroom, open **Settings > Connections**: under **Connect an assistant** there is a card for each assistant with that address and the steps to connect it. The library's owner turns on **Allow assistants to connect** there first.

## Install the skill

For Claude Code and Codex, and other assistants that read skills from your computer, use the open `skills` installer (it needs Node.js):

```sh
npx skills add origalabs/paperroom -g
```

`-g` installs the skill for you in every folder rather than in the current project only. The installer asks which assistants to install it for; name one to skip that question:

```sh
npx skills add origalabs/paperroom -g -a claude-code
npx skills add origalabs/paperroom -g -a codex
```

Add `-y` to answer the installer's other questions with yes.

## Claude on the web and in the Claude apps

claude.ai takes a skill as a ZIP. Your Paperroom serves it: open **Settings > Connections** and choose **Download the skill** on the Claude card, or open `/guide/paperroom-skill.zip` at your Paperroom's address. Then:

1. In Claude, open **Settings > Capabilities** and turn on **Code execution and file creation** (**Create and edit files** in newer settings), which skills need. On a Team or Enterprise plan an Owner allows skills for the organisation.
2. Open **Customize > Skills**, choose **+**, then **Create skill**, then **Upload a skill**, and choose `paperroom-skill.zip`.

The ZIP holds one file, `paperroom/SKILL.md`: the skill as your version of Paperroom carries it.

Paperroom also sends a short version of the skill to every assistant when it connects, so an assistant without the skill, ChatGPT among them, still gets the essentials.

## Licence

MIT. See [LICENSE](LICENSE).

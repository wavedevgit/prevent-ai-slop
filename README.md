# Prevent AI Slop

An attempt to prevent ai slop on open source repositories

# AGENTS.md method

## How this works

- Most AI coding tools have a set of instructions they follow from a MarkDown file called `AGENTS.MD` or `CLAUDE.MD`
- Thanks to those files, we can add instructions and magic words to make the ai refuse to work on your repo

## Why this works

- This will make the ai refuse to answer making it harder to make ai slop for people that don't know the file exists.
- For people that know how to use ai coding tools and reviews the code, they'll just delete the MarkDown files.

## How to use

- Add the all the MarkDown files in this repo to your repo (CLAUDE.md, AGENTS.md)
- That's it!

# Workflow method

## How this works

- When a pr is created, the workflow checks if:
    - The pr has claude or codex in co-authors
    - The pr has made with claude or any strings that leak that the pr was made with ai agents/tools
- If any of those rules match, we auto close the pr with a comment.

## Why this works

- This works because most ai agents/tools add theirselves to co-authors of prs and add a message in the pr message like `made with claude`

## How to use

- Add the workflow `./github/workflows/block_aislop_prs.yml` to your repo
- Modify it to use your own messages to your likings if you want
- That's it

### Using both methods is recommended, as it will block ai tools from writing code if the pr method doesn't work.

Made with ❤️ by [@wavedevgit](https://github.com/wavedevgit).

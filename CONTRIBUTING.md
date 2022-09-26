Check `Guides/`!

## Table of Contents

<details>
<summary>Click to expand</summary>

[[_TOC_]]

</details>

## VCS

- Clone the repository if you haven't already
- Create a new branch
- Work in the new branch
- Open an MR
- ???
- Profit

## Developing

1. If you're using Windows, make sure to not mess your line endings. I've added an `.editorconfig` file to help, but it'll still let stuff through, depending on if what you're using has [EditorConfig](https://editorconfig.org/) support. So, if you're using Windows, just `git config --global core.autocrlf true`
2. Feel free to use all Obsidian plugins installed liberally. Some things are still missing, for example the Obsidian Admonitions plugin uses different syntax than the MkDocs plugin. In these cases, just use Obsidian syntax and I'll be patching the MkDocs integration here and there to have more things rendered
3. Currently, the Markdown files inside `docs/` (aka the Obsidian Vault) that reside in `Excalidraw`, `Templates`, and in `Kanban` are excluded from the website generation using `mkdocs-exclude`. If you want to exclude anything else, `mkdocs.yml` is the place to check
4. If you don't want to add notes but instead want to change something MkDocs-related, or download additional Obsidian plugins or further configure Obsidian, feel free to open a descriptive MR. If you want to further configure Obsidian, please make sure to edit the `LOG.md` appropriately
5. Make sure that large-ish, non-Markdown files are tracked by [LFS](https://git-lfs.github.com/). For now, I've added LFS support for `*.pdf`, `*.png` and `*.jpg` files.

## General

This repository and webpage are and should remain public. This means you have to:
1. Write everything in English
2. Make sure there's no vulgar language, etc.
3. Avoid to include private information (e.g. files under NDA). If you want to refer to such a file, just mention it and a link to the actual file to our Google Drive or Nextcloud instance, or (private) GitLab issue, instead of commiting the information in this repository

This is still our notes.
Nothing else, nothing more.
You can more rough notes, informal, but well written.
Strive to have all notes and drawings, etc., atomic.

Each MR will be reviewed by @xlxs4 (subject to change) in order to ensure some basic consistency and to make sure there's nothing that breaks the above 3 rules.
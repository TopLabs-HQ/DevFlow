<h1 align="center">DevFlow</h1>

<p align="center">Notes, tasks and Git for developers, in one fast Linux app.<br>
Your files stay plain Markdown on your disk. No account, no cloud, works offline.</p>

---

## Install

| Your system | How |
|---|---|
| **Arch Linux** | `git clone https://github.com/TopLabs-HQ/DevFlow && cd DevFlow/arch && makepkg -si` (installs the official build as a native package), or use the `.AppImage` |
| **Debian / Ubuntu** | Download the `.deb` from [Releases](https://github.com/TopLabs-HQ/DevFlow/releases), then `sudo apt install ./DevFlow_*.deb` |
| **Fedora / openSUSE** | Download the `.rpm` from [Releases](https://github.com/TopLabs-HQ/DevFlow/releases), then `sudo dnf install ./DevFlow-*.rpm` |
| **Any other distro** | Download the `.AppImage` from [Releases](https://github.com/TopLabs-HQ/DevFlow/releases), then `chmod +x DevFlow_*.AppImage` and run it |

DevFlow needs `git` installed for the Git features. To stay signed in to GitHub between sessions, you need a keyring such as GNOME Keyring or KWallet; most desktops already have one.

## Getting started

1. **Open DevFlow and click Open folder.** Pick any folder: an existing project, a notes folder or an empty one. DevFlow works with the files that are already there. It doesn't move them, rename them or add anything of its own to the folder.
2. **Press `Ctrl+N` to write your first note.** Everything saves automatically.
3. **Press `Ctrl+K` any time.** The command palette lists every action and lets you jump to any note.

On the far left, a thin bar switches between the five areas:

| | Area | Shortcut | What it's for |
|---|---|---|---|
| 📖 | **Notes** | `Ctrl+1` | Write and browse your files |
| ☑️ | **Tasks** | `Ctrl+2` | Everything you have to do, with reminders |
| ⑂ | **Changes** | `Ctrl+3` | What you changed: review, stage, commit |
| 🕘 | **History** | `Ctrl+4` | Past commits and what each one changed |
| ⇄ | **Pull requests** | `Ctrl+5` | Your project's GitHub pull requests |

Changes, History and Pull requests appear once the folder is a Git repository.

## Notes

- **Write in Markdown.** Headings, lists, `code` and fenced code blocks are all styled as you type. Code blocks get syntax highlighting for more than 100 languages.
- **Link notes** by typing `[[` and picking a note. `Ctrl+click` a link to follow it. If the note doesn't exist yet, DevFlow offers to create it.
- **Backlinks.** The panel on the right lists every note that links to the one you're reading, plus an outline of its headings. Toggle the panel with `Ctrl+\`.
- **Tags.** Write `#tag` anywhere, or `tags: [api, backend]` at the top of a note. Click a tag in the sidebar to see every note that has it.
- **Search everything** with `Ctrl+Shift+F`. Results appear instantly as you type.
- **Read view.** `Ctrl+E` switches between editing and a clean rendered page.
- **Decision records.** `Ctrl+Shift+D` creates a numbered record in `decisions/` with Context, Decision and Consequences sections, so you remember *why* you chose something.
- **Any file.** Code files open with highlighting and line numbers and can be edited. Images and PDFs show a preview. Other files can be opened with your system's default app. DevFlow refuses to hand off programs and scripts this way, for your safety.
- **Nothing gets lost.** If another program changes a file while you're editing it, DevFlow asks which version to keep. Deleted files go to your system Trash.

## Tasks and reminders

Any checkbox in any note is a task:

```markdown
- [ ] Write the release notes
- [ ] Review Ana's PR @due(2026-10-20)
- [ ] Call the client @due(2026-10-20 15:30)
- [x] Fix the login bug
```

- **The Tasks view (`Ctrl+2`)** collects every task from every note and groups them into **Overdue**, **Today**, **Next 7 days**, **Later** and **No date**.
- **Add tasks fast** with `Ctrl+Shift+T` and plain words:
  - "Review PR **tomorrow 15:00**"
  - "Renew certificate **in 3 days**"
  - "Retro **next mon**"
  - "Deploy **fri**"
  - "Ship it **2026-11-02**"

  Quick-added tasks go to `Inbox.md`.
- **Reminders.** When a task is due, you get a desktop notification. A task with only a date reminds you at 09:00 that day. DevFlow has to be running for reminders to appear.
- **Tick a task** in the Tasks view and DevFlow updates the checkbox in the note itself. Click a task to jump to the note it came from.
- The amber badge on the Tasks icon counts overdue tasks.

## Git

DevFlow covers what you need day to day, the same things GitHub Desktop does.

**Trusting a project first.** When you open a folder that already contains a Git repository, click **Trust this Git repository** in the bottom-left corner. Git can run programs configured inside a repository, so DevFlow runs no Git commands until you say the project is yours or that you trust it. Projects you clone or create with DevFlow are trusted automatically.

**Changes (`Ctrl+3`)**
- The left side lists changed files; the right side shows exactly what changed.
- **Stage** a file with its checkbox or `Space`, or stage just one block of it with **Stage hunk**.
- **Discard** changes from a file's right-click menu. The old version goes to the Trash, so you can still get it back.
- **Commit:** write a summary, an optional description, then click **Commit to main** or press `Ctrl+Enter`.
  - **Amend** changes the last commit.
  - **Co-authors** credits teammates.
- **Stash** puts changes aside for later and brings them back, from the **Stashed changes** row.

**Branches and syncing.** Use the buttons at the top of Changes and History.
- The **branch button** lets you switch, create, rename, delete or merge branches.
- The **sync button** always shows the next step: **Publish branch**, **Pull**, **Push** or **Fetch**.

**History (`Ctrl+4`).** Click a commit to see its files and changes. Right-click it to:
- copy its ID
- create a branch or tag from it
- revert it or cherry-pick it
- undo it, if it's your latest commit and you haven't pushed it yet

**Conflicts.** If a merge or pull conflicts, Changes lists the conflicting files. For each one, choose **Use mine** or **Use theirs**, or edit the file and click **Mark resolved**. Then click **Continue**, or click **Abort** to go back to how things were.

## GitHub (optional)

1. Open **Settings** (`Ctrl+,`), go to **GitHub** and click **Connect**.
2. Choose what DevFlow may access:
   - **public repositories only**
   - **public and private repositories**
3. Click **Copy code and open GitHub**, paste the code there and approve.

Your sign-in is stored in your system keyring, never in a file.

Then you can:
- **Clone** any of your repositories and open it as a workspace.
- **Publish** a folder as a new GitHub repository.
- **Work with pull requests (`Ctrl+5`):**
  - read the description, comments, checks and changed files
  - open a new PR from your current branch
  - merge, squash or rebase
  - close or reopen, and comment
  - **Check out branch** to try a PR locally

To disconnect, go to Settings, then GitHub, then **Sign out**. You can also revoke DevFlow at any time in [GitHub → Settings → Applications](https://github.com/settings/applications).

## Keyboard shortcuts

| Action | Keys |
|---|---|
| Command palette | `Ctrl+K` |
| Open a note | `Ctrl+P` |
| Search all notes | `Ctrl+Shift+F` |
| New note / decision record | `Ctrl+N` / `Ctrl+Shift+D` |
| Quick-add task | `Ctrl+Shift+T` |
| Switch area | `Ctrl+1` … `Ctrl+5` |
| Edit / read view | `Ctrl+E` |
| Sidebar / details panel | `Ctrl+B` / `Ctrl+\` |
| Find in note | `Ctrl+F` |
| Follow a `[[link]]` | `Ctrl+click` |
| Commit (in Changes) | `Ctrl+Enter` |
| Git sync | `Ctrl+Shift+S` |
| Open folder / settings | `Ctrl+O` / `Ctrl+,` |

In the file tree, arrow keys move, `Enter` opens, `F2` renames and `Delete` moves the item to the Trash. Vim keybindings can be turned on in Settings.

## Your data and privacy

- **Your notes are ordinary `.md` files** in the folder you chose. Open them with any editor, sync them with anything, back them up any way you like. If you stop using DevFlow, nothing is locked in.
- DevFlow keeps only a search index (in `~/.cache/devflow/`, safe to delete) and its settings (in `~/.config/devflow/`).
- **No telemetry and no account.** DevFlow connects to the internet only when you use GitHub features or push and pull with Git.

## Troubleshooting

| Problem | Fix |
|---|---|
| Blank window or crash on start with an NVIDIA card | DevFlow applies the usual fix automatically. If it still happens, start it with `WEBKIT_DISABLE_DMABUF_RENDERER=1 devflow` |
| Search results look out of date | Close DevFlow, delete `~/.cache/devflow/` and reopen it |
| GitHub sign-in is forgotten after restart | Install and run a keyring (`gnome-keyring` or `kwallet`) |
| "Trust this repository first" | Click **Trust this Git repository** in the bottom-left corner |
| Push or pull fails | For `git@github.com:` remotes, make sure your SSH key works in a terminal (`ssh -T git@github.com`) |
| No reminders | DevFlow must be running, and Settings → Reminders must be on |

## Feedback

Found a bug or have an idea? Open an [issue](https://github.com/TopLabs-HQ/DevFlow/issues).

## License

DevFlow is free to download and use, for personal and commercial work. It is proprietary software: copying, modifying or redistributing it is not allowed. See [LICENSE](LICENSE).

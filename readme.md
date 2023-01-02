<div align="center">

# gh look

Drop an emoji, write comments, star repositories, read the preview or browse the issue tracker. All interactively by combining `gh` with `fzf`.

![](https://user-images.githubusercontent.com/92653266/210178720-24bc78ef-5ae6-414c-8007-862a2a8f087e.gif)

</div>

---

## 💻 Requirements
Install [Fuzzy Finder (fzf)](https://github.com/junegunn/fzf#installation)  and the [GitHub command line tool (gh)](https://github.com/cli/cli#installation), for example through Homebrew.

Optionally, also install [bat](https://github.com/sharkdp/bat#installation) to beautify the preview.

```zsh
brew install fzf gh bat

# install this extension
gh ext install LangLangBart/gh-look
# upgrade
gh ext upgrade LangLangBart/gh-look
# uninstall
gh ext remove LangLangBart/gh-look
```

---

## 👨‍💻 Usage

```
gh look [Command] [-Flags] [Search term]
```

| Command | Description                                                     | Example                               |
| :------ | :-------------------------------------------------------------- | :------------------------------------ |
| issue   | List Issues                                                     | gh look issue -r cli/cli involves:@me |
| pr      | List Pull Requests                                              | gh look pr                            |
| search  | Search 🔎 for GitHub repos                                       | gh look search keycastr               |
| star    | List starred ⭐️ repos (sorted by the time the user set the star) | gh look star                          |

| Flags | All commands                                                        | Example                     |
| :---- | :------------------------------------------------------------------ | :-------------------------- |
| -c    | Cache the response, for example `30s`, `15m`, `1h` (default: `20s`) | gh look star -c 15m         |
| -w    | Display the preview window upon start (default: hidden)             | gh look issue -w -r cli/cli |

| Flags | Issue/ pr command                                    | Example                      |
| :---- | :--------------------------------------------------- | :--------------------------- |
| -e    | Emoji to make a reaction[^1] (default: THUMBS_UP 👍 ) | gh look pr -e CONFUSED       |
| -o    | sorting order[^2] (default: created-desc)            | gh look issue -o updated-asc |
| -r    | Specify a repository (form: OWNER/REPO)              | gh look pr -r cli/cli        |

| Flags | Star ⭐️ command             | Example                |
| :---- | :------------------------- | :--------------------- |
| -u    | List stars of another user | gh look star -u ashtom |


[^1]: Valid emojis {THUMBS_UP 👍, THUMBS_DOWN 👎, LAUGH 😄, HOORAY 🎉, CONFUSED 😕, HEART ❤️, ROCKET 🚀, EYES 👀}
[^2]: Valid Ordering options {author-date,committer-date,created,interactions,reactions,updated}-{desc,asc}
  [GitHub Docs - Searching on GitHub](https://docs.github.com/en/search-github/searching-on-github)


### Hotkeys
- <kbd>?</kbd> shows a list of specific hotkeys defined for each command.
- <kbd>pgup</kbd>/<kbd>pgdn</kbd> switches between commands (macOS <kbd>fn+↑</kbd>/<kbd>fn+↓</kbd>), comments can be reached with <kbd>enter</kbd>/<kbd>esc</kbd>.

```mermaid
%% GitHub seems to not display fontawesome icons
%% https://mermaid.js.org/syntax/flowchart.html#basic-support-for-fontawesome
flowchart BT
    Stars([fa:fa-user Stars])-->|pgdn| Search([fa:fa-magnifying-glass Search])
    Search -->|pgup| Stars
    Search -->|pgdn| Issues
    Issues -->|pgup| Search
    subgraph Issue_and_PR[fa:fa-nonsenseValue]
        direction BT
        Issues([fa:fa-circle-dot Issues]) --> |pgdn|PullRequests([fa:fa-code-pull-request Pull Requests])
        PullRequests --> |pgup| Issues
    end
    subgraph Comment[fa:fa-nonsenseValue]
        Comments([fa:fa-comments Comments])
    end
    Issue_and_PR -->|enter| Comments
    Comments -->|esc| Issue_and_PR

style Issue_and_PR fill:transparent,stroke-width:1px,stroke:#1234
style Comment fill:transparent,stroke-width:0px
```

---

## 💪 Contributing

### Text validation
`Vale` is a grammar, style, and word usage linter for the English language. The rules are set in the [.vale.ini](.vale.ini) file. It doesn't have a way to auto fix issues at the moment, this must be done manually.

```zsh
# install, for example through Homebrew
brew install vale


# Downloading packages ...
vale sync

# check the repository
vale .
# see even suggestions
vale --minAlertLevel=suggestion .
```

* An optional installation of the [Vale extension](https://marketplace.visualstudio.com/items?itemName=errata-ai.vale-server) to display warnings and errors at once.

---

## 💁 FAQ

### Strange icons
- [NERD FONT](https://www.nerdfonts.com/cheat-sheet) icons are being used. If you see some `strange` icons, follow the steps in the link to install a better font: [powerlevel10k#fonts](https://github.com/romkatv/powerlevel10k#fonts)

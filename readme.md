<div align="center">

# gh look

Drop an emoji, write comments, star repositories, check workflow progress, browse issue trackers, search for repositories, ... all interactively by combining `gh` with `fzf`.

![](https://user-images.githubusercontent.com/92653266/210178720-24bc78ef-5ae6-414c-8007-862a2a8f087e.gif)

</div>

---

## 💻 Requirements
- [bat](https://github.com/sharkdp/bat#installation) - preview looks better
- [Fuzzy Finder (fzf)](https://github.com/junegunn/fzf#installation) - allow for interaction with listed data
- [GitHub command line tool (gh)](https://github.com/cli/cli#installation) - get the data from Github

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

```sh
gh look [Commands] [Flags] [Search term]
```

| Command   | Description                    | Example                               |
| :-------- | :----------------------------- | :------------------------------------ |
| i, issue  | List Issues                    | gh look issue -r cli/cli involves:@me |
| h, help   | Help                           | gh look h                             |
| p, pr     | List Pull Requests             | gh look pr -h                         |
| r, run    | List Workflow Runs             | gh look run -r microsoft/vscode -n 20 |
| s, search | Search for GitHub Repositories | gh look search -w keycastr            |
| st, star  | List Starred Repositories      | gh look star -u ashtom                |

- see available `Flags` for each command with `gh look [Command] -h` or interactively with <kbd>?</kbd>

### Hotkeys
- <kbd>shift-up</kbd>/<kbd>shift-down</kbd> switches between commands

```mermaid
%% GitHub seems to not display fontawesome icons
%% https://fontawesome.com/search
%% https://mermaid.js.org/syntax/flowchart.html#basic-support-for-fontawesome
flowchart BT

    Help([fa:fa-circle-question Help])
    Stars & Search & Issues & PullRequests  & Workflows -->|?| Help
    Search([fa:fa-magnifying-glass Search]) -->|shift-up| Stars([fa:fa-user Stars])
    Stars-->|shift-down| Search
    Search -->|shift-down| Issues
    Issues -->|shift-up| Search

    subgraph Issue_and_PR[fa:fa-nonsenseValue]
        Issues([fa:fa-circle-dot Issues]) --> |shift-down|PullRequests([fa:fa-code-pull-request Pull Requests])
        PullRequests --> |shift-up| Issues
    end

    subgraph Workflow[fa:fa-nonsenseValue]
        Workflows([fa:fa-circle-play Workflow Runs])
    end

    Workflows -->|shift-up| PullRequests
    PullRequests -->|shift-down| Workflows

    Comments([fa:fa-comments Comments])  <-- Enter/Esc --> Issue_and_PR


linkStyle default stroke-width:0.8px
style Workflow fill:transparent,stroke-width:0px
style Issue_and_PR fill:transparent,stroke-width:0.5px,stroke:#5b387c90
```

---

## 💪 Contributing
Routine code checks are handled with the [pre-commit](https://github.com/pre-commit/pre-commit) hook, customizations are done in the [.pre-commit-config.yaml](.pre-commit-config.yaml).

> *Pre-commit is a multi-language package manager for pre-commit hooks. You specify a list of hooks you want and **pre-commit manages the installation and execution** of any hook written in any language before every commit. Source: [pre-commit introduction](https://pre-commit.com/#introduction)*

```zsh
# install through homebrew or pip
brew pre-commit
pip install pre-commit

# install the git hook scripts
pre-commit install --hook-type commit-msg --hook-type pre-commit
# pre-commit installed at .git/hooks/commit-msg
# pre-commit installed at .git/hooks/pre-commit

# hook location
.git/hooks/pre-commit
.git/hooks/commit-msg
```

---

## 💁 FAQ

### Strange icons
- [NERD FONT](https://www.nerdfonts.com/cheat-sheet) icons are being used. If you see some `strange` icons, follow the steps in the link to install a better font: [powerlevel10k#fonts](https://github.com/romkatv/powerlevel10k#fonts)

### Ordering options
- to change the order in which elements are listed see for details: [GitHub Docs - Searching on GitHub](https://docs.github.com/en/search-github/searching-on-github)
  - Valid Ordering options: {author-date,committer-date,created,interactions,reactions,updated}-{desc,asc}

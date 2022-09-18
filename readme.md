# gh look
Drop an emoji, create a new issue/ comment, read the preview or browse the issue tracker. All interactive by combining `gh` and `fzf`.

![](https://raw.githubusercontent.com/LangLangBart/ImagePool/eff1b17b31ce05c60023bcbb59b61d1727eee7b8/storage/18_Sep_22_at_07_06_03_emoji.gif)

```zsh
# install
gh ext install LangLangBart/gh-look

# uninstall
gh ext remove LangLangBart/gh-look
```

### Requirements
Install `fzf` to use this extension, for example through Homebrew.

```zsh
brew install fzf
```

### Usage

```
gh look [Command] [-Flags] [Search term]
```

| Command | Description        |
| ------- | ------------------ |
| issue   | List issues        |
| pr      | List pull requests |

| Flags  | Description                                                                                                                    |
| ------ | ------------------------------------------------------------------------------------------------------------------------------ |
| <none> | List issues from current directory                                                                                             |
| -e     | Emoji to make a reaction (default: THUMBS_UP 👍 ) {CONFUSED,EYES,HEART,HOORAY,LAUGH,THUMBS_DOWN,THUMBS_UP,ROCKET}              |
| -o     | sorting order of issues (default: created-desc) {author-date,committer-date,created,interactions,reactions,updated}-{desc,asc} |
| -R     | Specify a repository (form: OWNER/REPO)                                                                                              |
| -w     | Display the preview window upon start (default: hidden)                                                                        |

### Contributing

#### Text validation
`Vale` is a grammar, style, and word usage linter for the English language. The rules are set in the [.vale.ini](../.vale.ini) file.

```zsh
# install, for example through Homebrew
brew install vale

vale .
# see even suggestions
vale --minAlertLevel=suggestion .
```

* An optional installation of the [Vale extension](https://marketplace.visualstudio.com/items?itemName=errata-ai.vale-server) to display warnings and errors at once.
* Unlike `ESLint`, `Vale` doesn't have a way to auto fix issues at the moment, this must be done manually. To display all warnings and errors run the following command.

### Roadmap
There' s still work being done on it, but that's the direction it's going to go.
- [ ] add support for PRs
- [ ] add a command for listing starred repository from oneself and others users  `gh look star -Flags ...`


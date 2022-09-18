# gh look
Drop an emoji, write comments, star repositories, read the preview or browse the issue tracker. All interactively by combining `gh` with `fzf`.

![](https://raw.githubusercontent.com/LangLangBart/ImagePool/eff1b17b31ce05c60023bcbb59b61d1727eee7b8/storage/18_Sep_22_at_07_06_03_emoji.gif)

### Requirements
Install `fzf` and `gh`, for example through Homebrew.

```zsh
brew install fzf gh

# install
gh ext install LangLangBart/gh-look

# uninstall
gh ext remove LangLangBart/gh-look
```

### Usage

```
gh look [Command] [-Flags] [Search term]
```

| Command | Description               |
| ------- | ------------------------- |
| issue   | List issues               |
| pr      | List pull requests        |
| star    | List starred repositories |

| Flags  | Description issue/ pr command                                                                                        |
| ------ | -------------------------------------------------------------------------------------------------------------------- |
| <none> | List issues/ pull requests                                                                                           |
| -e     | Emoji to make a reaction (default: THUMBS_UP 👍 ) {CONFUSED,EYES,HEART,HOORAY,LAUGH,THUMBS_DOWN,THUMBS_UP,ROCKET}     |
| -o     | sorting order (default: created-desc) {author-date,committer-date,created,interactions,reactions,updated}-{desc,asc} |
| -R     | Specify a repository (form: OWNER/REPO)                                                                              |
| -w     | Display the preview window upon start (default: hidden)                                                              |

| Flags  | Description star ⭐️ command                                 |
| ------ | ---------------------------------------------------------- |
| <none> | List your stars (sorted by the time the user set the star) |
| -U     | List stars from a user                                     |
| -w     | Display the preview window upon start (default: hidden)    |

### Contributing

#### Text validation
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

### FAQ
#### Strange icons
The `Star` command uses some [nerd font](https://www.nerdfonts.com/cheat-sheet) icons, such as the GitHub and Python logos. If you see some "strange" icons, follow the steps here to install a better font: [powerlevel10k#fonts](https://github.com/romkatv/powerlevel10k#fonts)

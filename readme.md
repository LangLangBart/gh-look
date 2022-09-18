# gh look
Drop an emoji, create a new issue/comment, read the preview or browse the issue tracker. All interactive by combining `gh` and `fzf`.

![](https://raw.githubusercontent.com/LangLangBart/ImagePool/eff1b17b31ce05c60023bcbb59b61d1727eee7b8/storage/18_Sep_22_at_07_06_03_emoji.gif)

```zsh
# install
gh ext install LangLangBart/gh-look

# uninstall
gh ext remove LangLangBart/gh-look
```

### Requirements
Install `fzf` to use this extension, for example via Homebrew.

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

| Flags  | Description                                                                                                                   |
| ------ | ----------------------------------------------------------------------------------------------------------------------------- |
| <none> | List issues from current directory                                                                                            |
| -e     | Emoji to make a reaction (default: THUMBS_UP 👍 ) {CONFUSED,EYES,HEART,HOORAY,LAUGH,THUMBS_DOWN,THUMBS_UP,ROCKET}              |
| -o     | sorting oder of issues (default: created-desc) {author-date,committer-date,created,interactions,reactions,updated}-{desc,asc} |
| -R     | Specify a repo (form: OWNER/NAME)                                                                                             |
| -w     | Display the preview window upon start (default: hidden)                                                                       |

### Roadmap
There' s still work being done on it, but that's the direction it's going to go.
- [ ] add support for PRs
- [ ] add a command for listing starred repos from oneself and others users  `gh look star -Flags ...`


# gh look
Drop an emoji, create a new issue/ comment, read the preview or search through the issue tracker are the things you can do with it. All interactive by combining `gh` and `fzf`.

![](https://raw.githubusercontent.com/LangLangBart/ImagePool/eff1b17b31ce05c60023bcbb59b61d1727eee7b8/storage/18_Sep_22_at_07_06_03_emoji.gif)

```zsh
# install
gh ext install LangLangBart/gh-look

# uninstall
gh ext remove LangLangBart/gh-look
```

### Prerequisites
Install `fzf` to use this extension, for example via Homebrew.

```zsh
brew install fzf
```

### Usage

```zsh
# list issues from the current directory
gh look

# lists issues from another repo and search for something
gh look -R cli/cli api zen
```

| Flag   | Description                                                                                                                  |
| ------ | ---------------------------------------------------------------------------------------------------------------------------- |
| <none> | List issues from current directory                                                                                           |
| -e     | Emoji to make a reaction (default: THUMBS_UP 👍 ) {CONFUSED,EYES,HEART,HOORAY,LAUGH,THUMBS_DOWN,THUMBS_UP,ROCKET}             |
| -o     | sorting oder of issues (default: created-desc) {author-date,committer-date,created,interactions,reactions,updated}-{desc,asc} |
| -R     | Specify a repo (form: OWNER/NAME)                                                                                            |
| -w     | Display the preview window upon start (default: hidden)                                                                      |

### TODO
- [ ] add support for PRs, 

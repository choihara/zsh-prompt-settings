# how to add git branch name on zsh prompt

### mac OS Catalina / iterm2

<img width="822" alt="screenshot" src="https://user-images.githubusercontent.com/88672609/128811445-96531ddf-3106-4445-85a7-f1a66810b51d.png"> <br />

`vi ~/.zshrc` to your terminal and copy + paste below:

```sh
# git
autoload -Uz vcs_info
setopt prompt_subst
zstyle ':vcs_info:git:*' check-for-changes true
zstyle ':vcs_info:git:*' unstagedstr "%F{yellow}? %f"
zstyle ':vcs_info:git:*' formats "%F{062}git::(%f%F{203}%b%f%F{062}) %f%c%u"
zstyle ':vcs_info:*' actionformats '[%b|%a]'3
precmd () { vcs_info }

PROMPT='%B%F{118}→%f%b %B%F{cyan}%~%F%b %B$vcs_info_msg_0_%b%F{white}
```

then `source ~/.zshrc`.

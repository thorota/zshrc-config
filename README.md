# zshrc-config
# エイリアス
alias ..='cd ../'
alias ...='cd ../..'
alias ....='cd ../../..'
alias mkdir='(){mkdir -p $1;cd $1}'

# git エイリアス
alias st='git status'

# ビープ音の停止(補完時)
setopt nolistbeep

# cd [TAB] で以前移動したディレクトリを表示
setopt auto_pushd

# 同じコマンドをヒストリに残さない
setopt hist_ignore_all_dups

# tab補完 色変更
autoload -Uz compinit
compinit
zstyle ':completion:*' menu select

# コマンド履歴入力補完
source ~/.zsh/zsh-autosuggestions/zsh-autosuggestions.zsh

# 現在地ディレクトリ表示
PS1="%{$fg[cyan]%}[${USER}@${HOST%%.*} %1~]%(!.#.$)${reset_color} "
PROMPT='%F{green}%~%f %n$ '

# 補完機能有効にする
autoload -U compinit
compinit -u

# 補完候補に色つける
autoload -U colors
colors
zstyle ':completion:*' list-colors "${LS_COLORS}"

# 単語の入力途中でもTab補完を有効化
setopt complete_in_word
# 補完候補をハイライト
zstyle ':completion:*:default' menu select=1

export DEV=/Users/rpc133/dev
alias dev='cd $DEV'

export PATH=$HOME/.nodebrew/current/bin:$PATH

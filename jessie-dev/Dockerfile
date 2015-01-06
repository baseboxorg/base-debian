FROM baseboxorg:baseimage-debian

RUN apt-get -q update
RUN apt-get install -y -q bash-completion && apt-get clean
RUN apt-get install -y -q zsh tmux git vim tig lftp tree moreutils realpath p7zip-full && apt-get clean
## Devel
#RUN apt-get install -y -q build-essential manpages && apt-get clean

## Checkout projects
WORKDIR /root/System
RUN git clone https://github.com/dhint/oh-my-zsh && cd oh-my-zsh && git checkout -b custom origin/custom
RUN git clone https://github.com/dhint/script-utils
RUN git clone https://github.com/dhint/dotfiles

## Custom env
WORKDIR /root
RUN mv .bashrc .bashrc.0 && \
  ln -s System/oh-my-zsh .oh-my-zsh && \
  ln -s System/dotfiles/bash/alias .alias  && \
  ln -s System/dotfiles/bash/bashrc .bashrc && \
  ln -s System/dotfiles/bash/custompath .custompath && \
  ln -s System/dotfiles/zsh/zshenv .zshenv && \
  ln -s System/dotfiles/zsh/zshrc .zshrc && \
  ln -s System/dotfiles/tmux/tmux.conf .tmux.conf && \
  ln -s System/dotfiles/vim .vim && \
  ln -s System/dotfiles/vim/vimrc .vimrc && \
  ln -s System/dotfiles/git/gitconfig .gitconfig

## Default shell
RUN chsh root -s /bin/zsh
CMD ["/bin/zsh"]
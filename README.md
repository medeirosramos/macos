# Ajustes MacOS by medeirosramos

## karabiner-macos

Software para MacOS https://karabiner-elements.pqrs.org/

### Minha customicação para as teclas Home e End nos Apps: Terminal/Notes

link para importação: [Home/End](http://karabiner://karabiner/assets/complex_modifications/import?url=https://raw.githubusercontent.com/medeirosramos/karabiner-macos/master/Home-End.json)

abra em seu navegador o link: *karabiner://karabiner/assets/complex_modifications/import?url=https://raw.githubusercontent.com/medeirosramos/karabiner-macos/master/Home-End.json*

## hist
editar o arquivo /etc/zshrc de:

HISTFILE=${ZDOTDIR:-$HOME}/.zsh_history  
HISTSIZE=2000  
SAVEHIST=1000  

para:

HISTFILE=${ZDOTDIR:-$HOME}/.zsh_history  
HISTSIZE=99999  
SAVEHIST=$HISTSIZE  
alias hist="history 1"  

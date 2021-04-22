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

## ssh-copy-id

ssh-copy-id -i .ssh/id_rsa.pub user@servidor.com.br


## multipass

multipass launch --name Ubuntu16 16.04

#Montar unidade hopedeiro
multipass mount /Users/rodrigo/gitntg maquina:/opt/gitntg
multipass umount maquina:/opt/gitntg

#definir primary
multipass set client.primary-name=Ubuntu20

#definir virtualizador
 sudo multipass get local.driver
 sudo multipass set local.driver=virtualbox
 ou
 sudo multipass set local.driver=hyperkit

#comandos diversos
 multipass info --all
 multipass list
 multipass delete demo
 multipass list
 multipass purge
 multipass list
 multipass get client.primary-name

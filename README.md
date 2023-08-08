# Ajustes MacOS by medeirosramos

## karabiner-macos

Software para MacOS https://karabiner-elements.pqrs.org/

Minha customizacao para as teclas Home e End nos Apps: Terminal/Notes

link para importacao: 
[Home/End](http://karabiner://karabiner/assets/complex_modifications/import?url=https://raw.githubusercontent.com/medeirosramos/karabiner-macos/master/Home-End.json)

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
alias servidores=/Users/rodrigo/github/macos/sshServidores.sh  
alias ireport=/Users/rodrigo/Downloads/iReport-5.6.0/bin/ireport  

## ssh-keygen
commando linux:
`ssh-keygen -t rsa -b 4096`

## ssh-copy-id

ssh-copy-id -i .ssh/id_rsa.pub user@servidor.com.br


## multipass

multipass launch --name ubuntu16 16.04
Launched: ubuntu16                                                              
Mounted '/Users/rodrigo' into 'ubuntu16:Home'  

#Montar unidade hopedeiro  
multipass??mount??/Users/rodrigo/gitntg??maquina:/opt/gitntg  
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

# Converter imagem .DMG em .ISO

hdiutil convert origem.dmg -format UDTO -o destino.iso

# Gravar ISO PenDrive

diskutil list

diskutil unmountDisk /dev/disk3

sudo dd if=/Users/rodrigo/Downloads/OracleLinux-R8-U3-x86_64-dvd.iso of=/dev/disk3 bs=1m

# HomeBrew https://brew.sh/

Exemplo de uso: brew install pdftk-java

# ireport MacOS
./Downloads/iReport-5.6.0/bin/ireport

# DEV in MacOS (Appache/PHP/VisualStudioCode)
https://getgrav.org/blog/macos-monterey-apache-multiple-php-versions

alias code="/Applications/Visual\ Studio\ Code.app/Contents/Resources/app/bin/code"

# Executar .exe feito em Java no MacOS

"/Library/Internet Plug-Ins/JavaAppletPlugin.plugin/Contents/Home/bin/java" -jar /Users/rodrigo/Downloads/Assinador_CPA.exe

# SVN Client MacOS

https://subversion.apache.org/packages.html#osx
brew options subversion  
brew install subversion  

# Job Log para impressora Ricoh
https://discussions.apple.com/thread/8658692
Terminal: 
sudo cupsctl WebInterface=yes
Browser:
http://127.0.0.1:631/printers/yourprinter
Administration -> Set Default Options -> Job Log -> Enable User Code: On
                                                    User Code: Custom 
                                                    User Code: xxxx
                Button Set Default Options
Terminal: 
sudo cupsctl WebInterface=no

Restart Print System or Reboot.

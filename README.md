## Ajustes MacOS by medeirosramos

### karabiner-macos

Software para MacOS https://karabiner-elements.pqrs.org/

Minha customizacao para as teclas Home e End nos Apps: Terminal/Notes

link para importacao: 
[Home/End](http://karabiner://karabiner/assets/complex_modifications/import?url=https://raw.githubusercontent.com/medeirosramos/karabiner-macos/master/Home-End.json)

abra em seu navegador o link: *karabiner://karabiner/assets/complex_modifications/import?url=https://raw.githubusercontent.com/medeirosramos/karabiner-macos/master/Home-End.json*

#### hist
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

### ssh-keygen
commando linux:
```
ssh-keygen -t rsa -b 4096
```

### ssh-copy-id
```
ssh-copy-id -i .ssh/id_rsa.pub user@servidor.com.br
```

### multipass
```
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
```
### Gerar HASH arquivo
```
shasum -a 256 exemplo.txt
# 45f873de9f8cb637345d6e66a583762730bbea30277ef7b32c9c3bd6700a32b2 exemplo.txt
echo "45f873de9f8cb637345d6e66a583762730bbea30277ef7b32c9c3bd6700a32b2 exemplo.txt" | shasum -a 256 --check
```

### Converter imagem .DMG em .ISO
```
hdiutil convert origem.dmg -format UDTO -o destino.iso
```
### Gravar ISO PenDrive
```
diskutil list

diskutil unmountDisk /dev/disk3

sudo dd if=/Users/rodrigo/Downloads/OracleLinux-R8-U3-x86_64-dvd.iso of=/dev/disk3 bs=1m
```
### JAVA
[alternatives](https://medium.com/@devkosal/switching-java-jdk-versions-on-macos-80bc868e686a)
```
/usr/libexec/java_home -V

export JAVA_HOME=`/usr/libexec/java_home -v 1.8.0_281`

```
##### Maven
```
export PATH=/Users/rodrigo/Projetos/JAVA/apache-maven-3.9.6/bin:$PATH
export PATH=/Users/rodrigo/Projetos/JAVA/apache-maven-3.2.5/bin:$PATH
```

### HomeBrew https://brew.sh/

Exemplo de uso: brew install pdftk-java

### ireport MacOS
./Downloads/iReport-5.6.0/bin/ireport

### Executar .exe feito em Java no MacOS

"/Library/Internet Plug-Ins/JavaAppletPlugin.plugin/Contents/Home/bin/java" -jar /Users/rodrigo/Downloads/Assinador_CPA.exe


## DEV in MacOS (Appache/PHP/VisualStudioCode)
https://getgrav.org/blog/macos-monterey-apache-multiple-php-versions

alias code="/Applications/Visual\ Studio\ Code.app/Contents/Resources/app/bin/code"

## SVN Client MacOS

https://subversion.apache.org/packages.html#osx
brew options subversion  
brew install subversion  

### Job Log para impressora Ricoh  
https://discussions.apple.com/thread/8658692  
Terminal: `sudo cupsctl WebInterface=yes`  
Browser: http://127.0.0.1:631/printers/yourprinter  
Administration -> Set Default Options -> Job Log:  
Enable User Code: On  
User Code: Custom   
User Code: xxxx  
Button Set Default Options  
Terminal: `sudo cupsctl WebInterface=no`  
Restart Print System or Reboot.  

### GlobalProtect  

Listar rotas: `netstat -nr -f inet`  
Conecta na VPN (rota defult para utun4 terá prioridade)  
Remov. rota padrão ETH0: `sudo route delete default -interface en0`  
Adici. rota padrão ETH0: `sudo route add default -interface en0`  

Os comandos anteriores colocará a rota p/ ETH) como prioridade

Adici. rota da rede: `sudo route add 10.1.4.0 -netmask 255.255.255.0 -interface utun4`  

opcos para análise:  
`sudo route add 10.1.2.0 -netmask 255.255.255.0 -gateway 192.168.60.55`  
`sudo route add 10.1.3.0 -gateway 192.168.60.55`  
`sudo route add 10.1.4.0 -netmask 255.255.255.0  -gateway 192.168.60.55`  

### Captura de Tela
Comando para ler valores:
`defaults read com.apple.screencapture`  
Também é possivel acessar o arquivo de preferências: ~/Library/Preferences/com.apple.screencapture.plist  

Comando para configuração padrão:  
`defaults write com.apple.screencapture name "Captura de Tela"`  
`defaults write com.apple.screencapture "include-date" 1`  
`defaults write com.apple.screencapture type PNG`  

Comando para redefinir padrão SEM DATA:  
`defaults write com.apple.screencapture name "Captura de Tela"`  
`defaults write com.apple.screencapture "include-date" 0`  
`defaults write com.apple.screencapture type JPG` outros formatos possíveis: gif, pdf, tiff  
Não encontrei uma forma de remover os espaços e acento do modelo padrão "Captura de Tela yyyy-MM-dd às hh.mm.ss"

links de ref.:  
https://www.vpsbasics.com/software/how-to-change-default-screenshot-file-format-to-jpg-and-other-formats-with-macos/  
https://www.reddit.com/r/MacOS/comments/11jgajw/how_to_change_the_comapplescreencapture_name_to/?rdt=53048  

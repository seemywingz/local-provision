Provision Local Mac OsX
=====================================
###### !! Make sure to watch the teminal durring install, your user password is required !! 
## Prerequisites  
  * [Optional] Update the Desired Tools and Apps  
    *  playbooks/group_vars/all.yml 
    *  Current List:  

 cli_tools:
  - autojump
  - ctags
  - coreutils
  - curl 
  - fswatch
  - git
  - git-town
  - go
  - htop
  - jq
  - neovim
  - nmap
  - shellcheck
  - tree
  - watch
  - wget
  - yarn
  - zsh

cask_apps:
  - 1password
  - docker
  - intellij-idea
  - iterm2
  - java8
  - postman
  - sequel-pro
  - slack
  - spotify
  - tunnelblick
  - visual-studio-code-insiders
  - zeplin

# Run the Setup
The setup script will install both [Homebrew](https://brew.sh/) and [Ansible](https://www.ansible.com/overview/how-ansible-works)  
Then Ansible will take care of the rest!

#### Default Setup
  `./setup.sh`

#### Limit Which Tasks to Run  ["cli","apps","dotfiles"]
  `./setup.sh -t "cli,apps"`

#### To Exclude Tasks ["cli","apps","dotfiles"]
  `./setup.sh -e "dotfiles"`
  

# Caveats
#### !! Make sure to watch the teminal durring install, your user password is required !! 

#### ZSH
To change your shell to ZSH
```shell_session 
chsh -s /bin/zsh
```  

#### Java8
If you chose not to use the provided dotfiles, make sure to set the proper `JAVA_HOME` environment variable in your shell's run commands e.g. `~/.bashrc` 
```
export JAVA_HOME=`/usr/libexec/java_home -v 1.8`
```
Java8 Brew Caveats 
###### As of September 20, 2018 latest Java8 version is: 1.8.0_181
```shell_session
java8: 1.8.0_181-b13,96a7b8442fe848ef90c96a2fad6ed6d1
https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html
/usr/local/Caskroom/java8/1.8.0_181-b13,96a7b8442fe848ef90c96a2fad6ed6d1 (243MB)
From: https://github.com/Homebrew/homebrew-cask-versions/blob/master/Casks/java8.rb
==> Name
Java Standard Edition Development Kit
==> Artifacts
JDK 8 Update 181.pkg (Pkg)
==> Caveats
This Cask makes minor modifications to the JRE to prevent issues with
packaged applications, as discussed here:

  https://bugs.eclipse.org/bugs/show_bug.cgi?id=411361

If your Java application still asks for JRE installation, you might need
to reboot or logout/login.

Installing java8 means you have AGREED to the license at
  https://www.oracle.com/technetwork/java/javase/terms/license/index.html
```

#### Vim
Vim should auto install `Vim-Plug`   
To install vim plugins with `Vim-Plug`
```
vim -c PlugInstall -c qa
```

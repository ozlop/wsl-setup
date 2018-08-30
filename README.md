# WSL Development Environment Setup
After a year or so of using Cygwin within older versions of Windows, I was
excited to get my hands on a machine capable of running Windows 10 and finally
get a chance to play with the WSL.

I've never looked back since then.

Here is a brief rundown of setup, configuration and modification of my
environment:
<br>


## WSL
### Enable WSL
* Follow [these](https://www.wikihow.com/Enable-the-Windows-Subsystem-for-Linux)
  instructions to enable WSL.

### Configuration
#### User

Create user and add to sudoers group
```bash
useradd <user>
usermod -aG sudo <user>
```

Tell Bash on Ubuntu to use username by default (run in cmd or powershell).
```
LxRun /setdefaultuser <user>
```

#### Host
Add host machine name (`$HOSTNAME`) to `/etc/hosts` file.

`vi /etc/hosts`

```
127.0.0.1 localhost
127.0.0.1 <$HOSTNAME>
```
<br>


## ZSH
### Installation

`sudo apt-get install zsh`

`vi ~/.bashrc`

### Configuration
#### Default Shell

`vi ~/.bashrc`

The following lines will ensure that Bash only launches Zsh when you open a Bash
window. This will avoid causing problems for other software.

```bash
if [ -t 1 ]; then
  exec zsh
fi
```
<br>

## Git
### Installation
Install git.

`sudo apt-get install git`


### Modifications
git log aliases
```bash
# Github log visualization
alias lg='git log \
  --graph \
  --abbrev-commit \
  --decorate \
  --format=format:"%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)"'
alias lg2='git log \
  --graph \
  --abbrev-commit \
  --decorate \
  --format=format:"%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(bold yellow)%d%C(reset)%n''%C(white)%s%C(reset) %C(dim white)- %an%C(reset)"'
alias lg3='git log \
  --graph \
  --abbrev-commit \
  --decorate \
  --format=format:"%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset) %C(bold cyan)(committed: %cD)%C(reset) %C(bold yellow)%d%C(reset)%n''%C(white)%s%C(reset)%n''%C(dim white)- %an <%ae> %C(reset) %C(dim white)(committer: %cn <%ce>)%C(reset)"'
```
<br>


## Hyper
## Installation
## Configuration
- gpu blacklist
 - Add `--ignore-gpu-blacklist` to hyper shortcut
- monokai theme
 - `plugins: ['hyperterm-monokai'],`
- fonts/size
 - inconsolata
<br>


## Oh-My-Zsh

https://github.com/robbyrussell/oh-my-zsh

# WSL Development Environment Setup
After a year or so of using Cygwin within older versions of Windows, I was
excited to get my hands on a machine capable of running Windows 10 and finally
get a chance to play with the WSL.

I've never looked back since then.

Here is a brief rundown of setup, configuration and modification of my
environment:


## WSL
### Enable WSL
* Follow [these](https://www.wikihow.com/Enable-the-Windows-Subsystem-for-Linux)
  instructions to enable WSL. 

### Configuration
Set change default user from root to new user

Create user
- useradd <user>

Add to sudoers
- usermod -aG sudo <user>

Tell Bash on Ubuntu to use username by default
- LxRun /setdefaultuser <user>

unable to resolve host error
rewrite  
`vi /etc/hosts`

```bash
127.0.0.1 localhost
127.0.0.1 <$HOSTNAME>
```

https://iamnotmyself.com/2016/07/13/windows-subsystem-for-linux-error-unable-to-resolve-host-2/



## Shell Configuration

### ZSH
#### Installation

`sudo apt-get install zsh`

`vi ~/.bashrc`

```bash
# Enable Zsh on startup
if [ -t 1 ]; then
  exec zsh
fi
```

rewrite below instructions  
https://medium.com/@uniqvinh/use-zsh-in-wsl-on-windows-10-5d439a749c4c



## Git

`sudo apt-get install git`

git log aliases





### Oh-My-Zsh

https://github.com/robbyrussell/oh-my-zsh


## hyper configuration
- gpu blacklist
 - Add `--ignore-gpu-blacklist` to hyper shortcut
- monokai theme
 - `plugins: ['hyperterm-monokai'],`
- fonts/size
 - inconsolata

## Activate OpenUI5 support assistant
Keybind: CTRL-ALT-SHIFT-P

[Discuss](https://github.com/rsletta/til/issues/14)

<hr>

## Proxmox trying to acquire lock to stop VM - fix error
```
trying to acquire lock...
TASK ERROR: can't lock file '/var/lock/qemu-server/lock-<VM id>.conf' - got timeout
```

```shell
rm /var/lock/qemu-server/lock-<VM id>.conf
```

[Discuss](https://github.com/rsletta/til/issues/13)

<hr>

## Copy public key to remote server
```shell
ssh-copy-id username@remote_host
```

[Discuss](https://github.com/rsletta/til/issues/12)

<hr>

## Turn of IPv6 Raspian Strech install
Edit ```/etc/sysctl.conf```. 

```vim 
    net.ipv6.conf.all.disable_ipv6 = 1
```
Save

Modify kernel parameters

```bash
~ $ sudo sysctl -p
```

[Discuss](https://github.com/rsletta/til/issues/11)

<hr>

## Fix DNS issues on fresh Raspian Strech install
Edit ```/etc/dhcpcd.conf```. 

static domain_name_servers=1.1.1.1 1.0.0.1 208.69.38.205 8.8.8.8

[Discuss](https://github.com/rsletta/til/issues/10)

<hr>

## Install NVM with Homebrew
* Install NVM
```brew install nvm```

* Add NVM folder
```mkdir ~/.nvm  ```

* Add config to .bash_profile
export NVM_DIR="$HOME/.nvm"
. "/usr/local/opt/nvm/nvm.sh"

[Discuss](https://github.com/rsletta/til/issues/9)

<hr>

## Manage multiple Docker instances using Portainer agent
## Run instance of portainer agent on docker instance

```sh
docker run -d -p 9001:9001 --name portainer_agent --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v /var/lib/docker/volumes:/var/lib/docker/volumes portainer/agent
```
## Configure endpoint in Portainer on management instance

![agent-endpoint](https://user-images.githubusercontent.com/12566124/112557327-850d0580-8dcc-11eb-890d-f2aefe8171da.jpg)


[Discuss](https://github.com/rsletta/til/issues/8)

<hr>

## Keyboard identified wrong
If the keyboard has been identified wrong, for example ISO kb as ANSI kb

```shell
sudo rm /Library/Preferences/com.apple.keyboardtype.plist
```

Reboot - Use keybord assistant

[Discuss](https://github.com/rsletta/til/issues/7)

<hr>

## Rewrite commit author in Git repo
```shell
#!/bin/sh

git filter-branch --env-filter '

OLD_EMAIL="Wrong user e-mail"
CORRECT_NAME="User name"
CORRECT_EMAIL="User e-mail"

if [ "$GIT_COMMITTER_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_COMMITTER_NAME="$CORRECT_NAME"
    export GIT_COMMITTER_EMAIL="$CORRECT_EMAIL"
fi
if [ "$GIT_AUTHOR_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_AUTHOR_NAME="$CORRECT_NAME"
    export GIT_AUTHOR_EMAIL="$CORRECT_EMAIL"
fi
' --tag-name-filter cat -- --branches --tags
```

[Discuss](https://github.com/rsletta/til/issues/6)

<hr>

## Enable 2FA and access github repo
When 2FA is enabled, one must create a personal access token, and use that as password. Remote repo must be on HTTPS, not SSH.
[Using two-factor authentication with the command line](https://help.github.com/articles/accessing-github-using-two-factor-authentication/#using-two-factor-authentication-with-the-command-line)

[Discuss](https://github.com/rsletta/til/issues/5)

<hr>

## Fix commit author with git amend
```git commit --amend --author="Author Name <email@address.com>"```

[Discuss](https://github.com/rsletta/til/issues/4)

<hr>

## Extract git commit messages since <commit>
To quickly get list of events. Usefull for release notes etc...

```git log --format=%B <commit hash>..HEAD > filename.ext```

[Discuss](https://github.com/rsletta/til/issues/3)

<hr>

## PlantUML icons
* [PlantUML Office](https://github.com/Roemer/plantuml-office)
* [Cloudinsight PlantUML sprites](https://github.com/rabelenda/cicon-plantuml-sprites)
* [Open Iconic](https://useiconic.com/open/)
* [Material Design](https://github.com/Templarian/MaterialDesign)
* [AWS PlantUML](https://github.com/milo-minderbinder/AWS-PlantUML)


### Examples

Default (Open Iconic)
```
@startuml
listopeniconic
@enduml
```

Devicons / Font-awesome
```
@startuml
 
' Include common to use icon macros.
!include <devicons/common>
' Include icon from Devicons.
!include <devicons/github>
' Include icon from Font Awesome icons.
!include <font-awesome/gitlab>
 
' Use macros from common library.
' First argument is alias, second label.
DEV_GITHUB(github, 'Github')
FA_GITLAB(gitlab, 'Gitlab')
 
' Use ~ to escape #
github -> gitlab : ~#movingtogitlab
 
@enduml
```

[Discuss](https://github.com/rsletta/til/issues/2)

<hr>

## Install PlantUML
macOS:

```sh
 brew install plantuml
 ```

[Discuss](https://github.com/rsletta/til/issues/1)

Ansible role: zsh-kali
=========

Ansible role that installs zsh and sets as users default shell. The [.zshrc from kali linux](https://gitlab.com/kalilinux/packages/kali-defaults/-/blob/kali/master/etc/skel/.zshrc) is used with auto completion and suggestions enabled by default too.

Example:
~~~
┌──(gadgieOps@xps)-[~/Projects/gadgieOps.zsh-kali]
└─$ 
~~~

For a richer and more customizable zsh experience: [oh my zsh](https://github.com/ohmyzsh/ohmyzsh)

Role Variables
--------------
<br>

~~~
aliases:
  - alias: "string"
    command: "string"
~~~
aliases is a list of dictionaries containing two keys: "alias" and "command". Allows of setting persistant aliases in .zshrc.
<br>
<br>

~~~
prompt_symbol: "string"
~~~

prompt_symbol allows to change the default kali prompt symbol (㉿).
<br>
<br>

~~~
install_auto_completion: bool
~~~

install_auto_completion toggles whether or not to install [zsh autocompletion](https://github.com/zsh-users/zsh-completions). Default: true
<br>
<br>

~~~
install_auto_suggestion: bool
~~~

install_auto_suggestion toggles whether or not to install [zsh autosuggestion](https://github.com/zsh-users/zsh-autosuggestions). Default: true
<br>
<br>

Example Playbook
----------------

~~~
- hosts: localhost
  roles:
  - role: gadgieOps.zsh-kali
    vars:
      prompt_symbol: "@"
      aliases:
      - alias: k
        command: kubectl
      - alias: vi
        command: vim
~~~

result:
~~~
┌──(gadgieOps@xps)-[~/Projects/gadgieOps/ha-kubernetes]
└─$ k get nodes
NAME      STATUS   ROLES           AGE     VERSION
barry     Ready    control-plane   10m     v1.25.4
maurice   Ready    control-plane   10m     v1.25.4
robin     Ready    control-plane   10m     v1.25.4
~~~

Support
-------
Tested on:
- Ubuntu 22.04
- CentOS Linux 7


License
-------

MIT

Author Information
------------------

Authored by gadgieOps.

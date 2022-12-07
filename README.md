zsh-kali
=========

Ansible role that installs zsh and sets as users default shell. The [.zshrc from kali linux](https://gitlab.com/kalilinux/packages/kali-defaults/-/blob/kali/master/etc/skel/.zshrc) is used with auto completion and suggestions enabled by default too.

Example:
~~~
┌──(gadgieOps@xps)-[~/Projects/gadgieOps.zsh-kali]
└─$ 
~~~

Tested on:
- Ubuntu 22.04
- CentOS Linux 7

Role Variables
--------------

~~~
aliases:
  - alias:
    command:
~~~

aliases is a list of dictionaries containing two keys: "alias" and "command". Allows of setting persistant aliases in .zshrc.  


~~~
prompt_symbol: "string"
~~~

prompt_symbol allows to change the default kali prompt symbol (㉿).   


~~~
install_auto_completion: bool
~~~

install_auto_completion toggles whether or not to install [zsh autocompletion](https://github.com/zsh-users/zsh-completions). Default: true   


~~~
install_auto_suggestion: bool
~~~

install_auto_suggestion toggles whether or not to install [zsh autosuggestion](https://github.com/zsh-users/zsh-autosuggestions). Default: true   



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


License
-------

MIT

Author Information
------------------

Authored by gadgieOps.

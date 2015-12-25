# fedora20

vagrant and chef for fedora20 development environment.

* vim (with lua)
* zsh
* tmux

## preparation

```
$ gem i berkshelf --no-ri --no-rdoc
$ berks vendor cookbooks
```

## install

```
$ vagrant up
$ vagrant ssh-config --host=vagrant > ssh.config
$ knife solo prepare vagrant@vagrant -F ssh.config
$ knife solo init .
$ knife solo cook -F ssh.config vagrant nodes/dev.json
```

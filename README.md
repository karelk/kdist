# kdist
Simple script for provisioning, configuration management, and deployment

Templates are stored in directory `$HOME/kdist/`

To create an empty template directory structure, do:

```
mkdir -p $HOME/kdist/my-template/{0-execute-before,1-install,2-transfer,3-execute-after}
```

The template directory structure looks like this:

`0-execute-before`: commands to be executed before

`1-install`: packages to install

`2-transfer`: files to copy

`3-execute-after`: commands to be executed after

Sample template is provided here: [my-template](my-template.tar.xz)


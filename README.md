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

Sample template is provided here: [my-template.tar.xz](my-template.tar.xz)

The scrtipt uses rsync transport when available, scp otherwise.

Typical use would be:

```
kdist --all my-server.domain.org my-template
```

non-standard options can be provided:

```
kdist [-all] [--install] [--transfer] [--scp] [--port=NUM] [--timeout=NUM] server template
```

where:

`--install`: install packages (skips steps 0,2,3)

`--transfer`: transfer files (skips steps 0,1,3)

`--all`: do all steps (0,1,2,3): execute commands, install, transfer

`--scp`: force scp transport

`--port=NUM`: specify ssh port (if non-standard port is used)

`--timeout=NUM]`: specify timeout for ssh and rsync/scp. Default is 1 second.


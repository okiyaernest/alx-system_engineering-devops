# 0x0A Configuration management

## Resources:books:
Read or watch:
* [Intro to Configuration Management](https://intranet.hbtn.io/rltoken/r-NmkYO8bxIKp2qEx2ZjKQ)
* [Puppet resource type: file](https://intranet.hbtn.io/rltoken/fuhnsI9_1_F4GrHwGT3GxA)
* [Puppet’s Declarative Language: Modeling Instead of Scripting](https://intranet.hbtn.io/rltoken/Fqmb5rnChQgYAypvKoTxAQ)
* [Puppet lint](https://intranet.hbtn.io/rltoken/oezu0m_hJ8nEVA6a9o17Tw)
* [Puppet emacs mode](https://intranet.hbtn.io/rltoken/N70cVw8mG3707He-OxjP1w)

---
## Learning Objectives:bulb:

*    All your files will be interpreted on Ubuntu 14.04 LTS
*    All your files should end with a new line
*    A README.md file at the root of the folder of the project is mandatory
*    Your Puppet manifests must pass puppet-lint version 2.1.1 without any errors
*    Your Puppet manifests must run without error
*    Your Puppet manifests first line must be a comment explaining what the Puppet manifest is about
*    Your Puppet manifests files must end with the extension .pp

---
## Note on Versioning

Your Ubuntu 14.04 VM should have Puppet 3.4 preinstalled.

You do not need to attempt to upgrade versions. This project is simply a set of tasks to familiarize you with the basic level syntax which is virtually identical in newer versions of Puppet.

The linked documentation is to Puppet 3.8 because the 3.4 documentation has been archived and is therefore more challenging to navigate. If you would like to upgrade anyway, click here (this will not affect how your code is checked). Puppet 5 Docs

Install puppet-lint
```
$ apt-get install -y ruby
$ gem install puppet-lint -v 2.1.1
```
---

### [0. Create a file](./0-create_a_file.pp)
* Using Puppet, create a file in /tmp.

Requirements:
*    File path is /tmp/school
*    File permission is 0744
*    File owner is www-data
*    File group is www-data
*    File contains I love Puppet

Example:
```
root@6712bef7a528:~# puppet-lint --version
puppet-lint 2.1.1
root@6712bef7a528:~# puppet-lint 0-create_a_file.pp
root@6712bef7a528:~# 
root@6712bef7a528:~# puppet apply 0-create_a_file.pp
Notice: Compiled catalog for 6712bef7a528.ec2.internal in environment production in 0.04 seconds
Notice: /Stage[main]/Main/File[school]/ensure: defined content as '{md5}f1b70c2a42a98d82224986a612400db9'
Notice: Finished catalog run in 0.03 seconds
root@6712bef7a528:~#
root@6712bef7a528:~# ls -l /tmp/school
-rwxr--r-- 1 www-data www-data 13 Mar 19 23:12 /tmp/school
root@6712bef7a528:~# cat /tmp/school
I love Puppetroot@6712bef7a528:~#
```

### [1. Install a package](./1-install_a_package.pp)
* Using Puppet, install puppet-lint.

Requirements:
*    Install puppet-lint
*   Version must be 2.1.1

Example:
```
root@d391259bf577:/# puppet apply 1-install_a_package.pp
Notice: Compiled catalog for d391259bf577.hsd1.ca.comcast.net in environment production in 0.10 seconds
Notice: /Stage[main]/Main/Package[puppet-lint]/ensure: created
Notice: Finished catalog run in 2.83 seconds
root@d391259bf577:/# gem list

*** LOCAL GEMS ***

puppet-lint (2.1.1)
root@d391259bf577:/#
```

### [2. Execute a command](./2-execute_a_command.pp)
* Using Puppet, create a manifest that kills a process named killmenow.

Requirements:
*    Must use the exec Puppet resource
*    Must use pkill

Example:

Terminal #0 - starting my process
```
root@d391259bf577:/# cat killmenow
#!/bin/bash
while [[ true ]]
do
    sleep 2
done

root@d391259bf577:/# ./killmenow
```
Terminal #1 - executing my manifest
```
root@d391259bf577:/# puppet apply 2-execute_a_command.pp
Notice: Compiled catalog for d391259bf577.hsd1.ca.comcast.net in environment production in 0.01 seconds
Notice: /Stage[main]/Main/Exec[killmenow]/returns: executed successfully
Notice: Finished catalog run in 0.10 seconds
root@d391259bf577:/# 
```
Terminal #0 - process has been terminated
```
root@d391259bf577:/# ./killmenow
Terminated
root@d391259bf577:/#
```
---

## Author
* **Ernest Okiya** - [ErnestOkiya](https://github.com/okiyaernest)

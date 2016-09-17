# Session Outline

## Overview of ansible

### What is Ansible?

### Why Ansible?
* Agent less

### Big Picture
* Inventory
* Config
* Modules
* Playbook
  * Plays
* Python and SSH
* JSON

### Ansible Needs
#### Control server/ Provisioning machine - Manager
* \*NIX variants only
* Python 2.6 +
* No Python 3

#### Remote server - Managed
* \*NIX + Windows
* Python 2.5+ (2.4 possible)
* SSH
* Remote Powershell for Windows
* No Python 3

## Overview of the lab setup
  * Vagrant & Virtualbox
  * Quick overview of the vagrant file
    * apm - Ansible Provisioning Machine. Where ansible runs
    * service - Remote server hosting the service (web)
    * db - Remote server hosting the database
    * syncing folders
  * Ansible code - `cd ../demo-lab/provisioning/ansible`
  * `vagrant up`
  * in another terminal `vagrant rsync-auto`

## Ansible installation
  * apt-get (Demo)
    * `vagrant ssh apm`
    * `sudo apt-get install ansible`
  * yum
  * pip

## Ansible Hello World
  * Our first interaction
    * `cd ansible` : This is our working directory
    * `ansible all -i inventory -u vagrant -k -m ping`
    * ssh fingerprint issue
      * `ssh vagrant@192.168.33.30` -- example
    * `ansible all -i inventory -u vagrant -k -m ping -vvvv`

  * Yaml!
    * _Whitespace_ finicky!
    * Start a document with ---
    * \# for comments
    * key value pairs -> a: b  (Note the space after colon)
    * for yaml enthusiasts - [refer here](http://www.yaml.org/refcard.html)

## Inventory Basics
* `ansible all -i inventory1 -m ping`
* Walk through `inventory1`
* groups
* children
* vars for hosts and groups
* Order of preference of vars
  * All < Group < Host

## Ansible config Basics
* Config order of preference
  * environment variable > ./ansible.cfg > ~/.ansible.cfg > /etc/ansible/ansible.cfg
  * first one wins! no merging
* [Reference](http://docs.ansible.com/ansible/intro_configuration.html)

## Summarizing what to watch out for
* Yaml finicky about whitespace and formatting

## Demo gotchas
* apm - needed sshpass
  * `sudo apt-get install sshpass`

## What is Not Covered
* Scaling out inventory
* Execution Types
* Var Prompts
* Handlers
* Templates
* Conditionals
* Roles
* Tags
* Site
* Pre and Post tasks

### vagrant commands
  * `vagrant up` : get all servers to startup
  * `vagrant global-status` : check if servers are running.
  * `vagrant ssh <<machine-name>>` (refer Vagrantfile): ssh ing into a specific machine
  * `vagrant destroy` : destroys the entire setup.
  * `vagrant rsync-auto` : syncs synced folders (refer Vagrantfile)

### ansible commands
  * `ansible all -i inventory -u vagrant -k -m ping` : running ping on all nodes
  * `ansible all -i inventory -u vagrant -k -m ping -vvvv` : earlier command with very verbose output, -vvv will be lesser, -vv even lesser, -v is normal
  * `ansible all -i inventory1 -m ping` : uses the inventory1 file to get host variables to execute the ping module

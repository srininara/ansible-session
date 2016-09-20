### vagrant commands
  * `vagrant up` : get all servers to startup
  * `vagrant global-status` : check if servers are running.
  * `vagrant ssh <<machine-name>>` (refer Vagrantfile): ssh ing into a specific machine
  * `vagrant destroy` : destroys the entire setup.
  * `vagrant rsync-auto` : syncs synced folders (refer Vagrantfile)

### ansible commands
  * `ansible` - shows up help
  * `ansible all -i inventory -u vagrant -k -m ping` : running ping on all nodes
  * `ansible all -i inventory -u vagrant -k -m ping -vvvv` : earlier command with very verbose output, -vvv will be lesser, -vv even lesser, -v is normal
  * `ansible all -i inventory1 -m ping` : uses the inventory1 file to get host variables to execute the ping module on all inventory nodes
  * `ansible datacenter -i inventory1 -m ping` : uses the inventory1 file to get host variables for 'datacenter' to execute the ping module on 'datacenter' nodes.
  * `ansible service_hosts -i inventory1 -m ping` : similar to the earlier one but applies to 'service_hosts' group
  * `ansible service1 -i inventory1 -m ping` : similar to the earlier one but applies to the 'service1' node
  * `ansible datacenter -m ping` : this will send the ping command to the datacenter group which is defined in the inventory file that is configured in ansible config (ansible.cfg)
  * `ansible datacenter -m command -a "apt-get update" --sudo` : executes this 'apt-get update' command across the datacenter group
  * `ansible service_hosts -m shell -a "echo $PATH"` : executes this 'echo $PATH' shell command across the service_hosts group


### ansible-doc commands
  * `ansible-doc` : shows up help
  * `ansible-doc -l` : lists modules
  * `ansible-doc -s apt` : shows snippet information on the apt module
  * `ansible-doc apt` : show detailed information on the apt module

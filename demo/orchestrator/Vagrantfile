require 'ipaddr'
require 'yaml'

vagrant_config = YAML.load_file('config.yml')
puts "Config: #{vagrant_config.inspect}\n\n"

Vagrant.configure("2") do |config|
    master_config = vagrant_config.fetch('master')
    master_ip = vagrant_config.fetch('ip').fetch('master')
    
    config.vm.box = "kbeaugrand/debian-docker"
    config.vm.box_version = "0.2"

    config.hostmanager.enabled = true
   
    config.vm.define "master" do |master|
        master.vm.hostname = "master"
        master.vm.network "private_network", ip: master_ip

        master.vm.provider "virtualbox" do |v, override|
            v.cpus = master_config.fetch('cpus')
            v.memory = master_config.fetch('memory')
            v.name = "master"
        end

        # Enable provisioning with a shell script. Additional provisioners such as
        # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
        # documentation for more information about their specific syntax and use.
        master.vm.provision "shell", path: 'scripts/configure_rancher_server.sh', args: [   master_ip, 
                                                                                            vagrant_config.fetch('default_password'), 
                                                                                            vagrant_config.fetch('version'),
                                                                                            vagrant_config.fetch('cluster').fetch('name') ]
    end

    # Nodes
    node_config = vagrant_config.fetch('node')
    (1..node_config.fetch('count')).each do |i|
        node_ip = IPAddr.new(vagrant_config.fetch('ip').fetch('node'))
    
        node_name = "node-%02d" % i

        config.vm.define node_name do |node|

            node.vm.hostname = node_name
            node.vm.network "private_network", ip: IPAddr.new(node_ip.to_i + i - 1, Socket::AF_INET).to_s

            node.vm.provider "virtualbox" do |v|
                v.cpus = node_config.fetch('cpus')
                v.memory = node_config.fetch('memory')
                v.name = node_name
            end
            
            # Enable provisioning with a shell script. Additional provisioners such as
            # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
            # documentation for more information about their specific syntax and use.
            node.vm.provision "shell", path: 'scripts/configure_rancher_node.sh', args: [
                                                                                        master_ip, 
                                                                                        vagrant_config.fetch('default_password'),
                                                                                        vagrant_config.fetch('cluster').fetch('name') ]
        end
    end
end

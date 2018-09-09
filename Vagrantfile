# coding: utf-8
Vagrant.configure("2") do |config|
    config.vm.box = "minimum/centos-7-docker"
    config.hostmanager.enabled = true
   
    host_number = 3
   
    config.vm.provider "virtualbox" do |v|
      v.cpus = 2
      v.memory = 2048
    end
   
    # Configuration du proxy sur les VMs vagrant
    if Vagrant.has_plugin?("vagrant-proxyconf")
      if ENV.has_key?('HTTP_PROXY') and ENV.has_key?('HTTPS_PROXY')
           config.proxy.http     = "#{ENV['HTTP_PROXY']}"
           config.proxy.https    = "#{ENV['HTTPS_PROXY']}"
           config.proxy.no_proxy = "localhost, 172.17.177.*"
       end
    end
   
    config.vm.define "master" do |master|
        master.vm.hostname = "master"
        master.vm.network "private_network", ip: "172.17.177.90"

        # Enable provisioning with a shell script. Additional provisioners such as
        # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
        # documentation for more information about their specific syntax and use.
        master.vm.provision "shell", inline: <<-SHELL
            yum update -y
            yum clean all
            rm -rf /var/cache/yum
             
            docker run -d --restart=unless-stopped -p 80:80 -p 443:443 rancher/rancher
            SHELL
    end

    # Nodes
    (1..host_number).each do |i|
        config.vm.define "node#{i}" do |node|
            node.vm.hostname = "node#{i}"
            node.vm.network "private_network", ip: "172.17.177.9#{i}"
            
            # Enable provisioning with a shell script. Additional provisioners such as
            # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
            # documentation for more information about their specific syntax and use.
            node.vm.provision "shell", inline: <<-SHELL
                yum update -y
                yum clean all
                rm -rf /var/cache/yum
             
                SHELL
        end
    end
end

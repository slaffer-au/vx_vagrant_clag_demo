
Vagrant.configure(2) do |config|
  
  config.vm.define "spine1" do |spine1|
	spine1.vm.box = "cumulus-vx-2.5.3"

    spine1.vm.hostname = "spine1"
    spine1.vm.network "private_network", virtualbox__intnet: "l1s1"
    spine1.vm.network "private_network", virtualbox__intnet: "l2s1"
    spine1.vm.network "private_network", virtualbox__intnet: "l3s1"
    spine1.vm.network "private_network", virtualbox__intnet: "l4s1"
    spine1.vm.network "private_network", virtualbox__intnet: "l5s1"
    spine1.vm.network "private_network", virtualbox__intnet: "l6s1"
    spine1.vm.network "private_network", virtualbox__intnet: "peerlink_s12"
    spine1.vm.network "private_network", virtualbox__intnet: "peerlink_s21"

    spine1.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
    end
    
    iter = 2
    
    spine1.vm.provider "virtualbox" do |v|
      1.upto(9) do |spine1|
        v.customize ["modifyvm", :id, "--nicpromisc" + iter.to_s, "allow-vms"]
        iter += 1 
      end
    end

  end

  config.vm.define "spine2" do |spine2|
	spine2.vm.box = "cumulus-vx-2.5.3"
    spine2.vm.hostname = "spine2"

    spine2.vm.network "private_network", virtualbox__intnet: "l1s2"
    spine2.vm.network "private_network", virtualbox__intnet: "l2s2"
    spine2.vm.network "private_network", virtualbox__intnet: "l3s2"
    spine2.vm.network "private_network", virtualbox__intnet: "l4s2"
    spine2.vm.network "private_network", virtualbox__intnet: "l5s2"
    spine2.vm.network "private_network", virtualbox__intnet: "l6s2"
    spine2.vm.network "private_network", virtualbox__intnet: "peerlink_s12"
    spine2.vm.network "private_network", virtualbox__intnet: "peerlink_s21"

    spine2.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
    end

  end


  config.vm.define "leaf1" do |leaf1|
	leaf1.vm.box = "cumulus-vx-2.5.3"

    leaf1.vm.hostname = "leaf1"
    leaf1.vm.network "private_network", virtualbox__intnet: "l1s1"
    leaf1.vm.network "private_network", virtualbox__intnet: "l1s2"
    leaf1.vm.network "private_network", virtualbox__intnet: "peerlink_l12"
    leaf1.vm.network "private_network", virtualbox__intnet: "peerlink_l21"

    leaf1.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
    end

  end

  config.vm.define "leaf2" do |leaf2|
	leaf2.vm.box = "cumulus-vx-2.5.3"

    leaf2.vm.hostname = "leaf2"
    leaf2.vm.network "private_network", virtualbox__intnet: "l2s1", nicpromisc: "allow-vms"
    leaf2.vm.network "private_network", virtualbox__intnet: "l2s2", nicpromisc: "allow-vms"
    leaf2.vm.network "private_network", virtualbox__intnet: "peerlink_l12", nicpromisc: "allow-vms"
    leaf2.vm.network "private_network", virtualbox__intnet: "peerlink_l21", nicpromisc: "allow-vms"
  
    leaf2.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
    end

  end


  config.vm.define "leaf3" do |leaf3|
	leaf3.vm.box = "cumulus-vx-2.5.3"

    leaf3.vm.hostname = "leaf3"
    leaf3.vm.network "private_network", virtualbox__intnet: "l3s1"
    leaf3.vm.network "private_network", virtualbox__intnet: "l3s2"
    leaf3.vm.network "private_network", virtualbox__intnet: "peerlink_l34"
    leaf3.vm.network "private_network", virtualbox__intnet: "peerlink_l43"

    leaf3.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
    end

  end

  config.vm.define "leaf4" do |leaf4|
	leaf4.vm.box = "cumulus-vx-2.5.3"

    leaf4.vm.hostname = "leaf4"
    leaf4.vm.network "private_network", virtualbox__intnet: "l4s1"
    leaf4.vm.network "private_network", virtualbox__intnet: "l4s2"
    leaf4.vm.network "private_network", virtualbox__intnet: "peerlink_l34"
    leaf4.vm.network "private_network", virtualbox__intnet: "peerlink_l43"
  
    leaf4.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
    end

  end

  config.vm.define "leaf5" do |leaf5|
	leaf5.vm.box = "cumulus-vx-2.5.3"

    leaf5.vm.hostname = "leaf5"
    leaf5.vm.network "private_network", virtualbox__intnet: "l5s1"
    leaf5.vm.network "private_network", virtualbox__intnet: "l5s2"
    leaf5.vm.network "private_network", virtualbox__intnet: "peerlink_l56"
    leaf5.vm.network "private_network", virtualbox__intnet: "peerlink_l65"

    leaf5.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
    end

  end

  config.vm.define "leaf6" do |leaf6|
	leaf6.vm.box = "cumulus-vx-2.5.3"

    leaf6.vm.hostname = "leaf6"
    leaf6.vm.network "private_network", virtualbox__intnet: "l6s1"
    leaf6.vm.network "private_network", virtualbox__intnet: "l6s2"
    leaf6.vm.network "private_network", virtualbox__intnet: "peerlink_l56"
    leaf6.vm.network "private_network", virtualbox__intnet: "peerlink_l65"
  
    leaf6.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
    end

  end

end

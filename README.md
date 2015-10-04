# Cumulus VX - CLAG Demonstration
### _A two-tier, eight switch topology of Cumulus VX switches in a MLAG setup deployed with Vagrant and provisioned with Ansible._


#### Prerequisites
  * VirutalBox must be installed
    * https://www.virtualbox.org/
  * Vagrant must be installed
    * https://www.vagrantup.com/
  * Ansible must be installed
    * http://www.ansible.com/
  * The Cumulus Linux module for Ansible must be installed
    * Once Ansible is installed, this is achieved with the command "ansible-galaxy install cumulus.CumulusLinux"
    

#### Topology
![Topology](https://github.com/slaffer-au/vx_vagrant_clag_demo/blob/master/Topology/Topology.jpg)


##### Description
  * The eth0 interface is connected to a VirtualBox NAT network for internet connectivity. 
  * CLAGs are formed as pictured above, with CLAG IP keepalive and messaging communication performed using interface _peerlink.4094_.
  * No CLAG backup IP is configured. In a real-world deployment, it is recommended to do this through the OOB network.
  * On the Spine switches, CLAG IDs 1-3 are used towards the Leaf switches. Each Leaf pair use only CLAG ID 1 towards the Spines.
  * Each switch uses a VLAN-aware bridge, trunking VLANs 1-100 with a native VLAN of 1.
  * SVIs are currently configured on VLAN 10 on all switches. The Spine switches also have VRR configured between them.
  



# Local 3-node test cluster (1 head + 2 compute) on Rocky Linux 9.
# Requires VirtualBox and Vagrant.  Usage: vagrant up
Vagrant.configure("2") do |config|
  config.vm.box = "rockylinux/9"

  {
    "head01" => "192.168.56.10",
    "node01" => "192.168.56.11",
    "node02" => "192.168.56.12"
  }.each do |name, ip|
    config.vm.define name do |node|
      node.vm.hostname = name
      node.vm.network "private_network", ip: ip
      node.vm.provider "virtualbox" do |vb|
        vb.name = name
        vb.cpus = 2
        vb.memory = 4096
      end
    end
  end
end

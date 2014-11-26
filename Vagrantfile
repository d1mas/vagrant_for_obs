# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    # box name and URL (URL is needed in this case for getting right box with puppet agent builded in)
    config.vm.box = "berendt/opensuse-13.1-x86_64"
    config.vm.box_url = "https://vagrantcloud.com/berendt/boxes/opensuse-13.1-x86_64/versions/3/providers/virtualbox.box"
    config.vm.box_check_update = false

    # box name in vagrant console
    config.vm.define "obs-server" do |obsserver|
    end

    # network config - change adapter name from "eth0" if needed
    config.vm.network "public_network", type: "dhcp", :bridge => "eth0"

    # vm settings inside vbox manager
    config.vm.provider "virtualbox" do |vb|
      vb.gui = true
      vb.name = "obs-server_puppet"
      vb.customize ["modifyvm", :id, "--memory", "512"]
    end

    # puppet settings and paths
    config.vm.provision :puppet do |puppet|
      puppet.manifests_path = "puppet-manifests/manifests"
      puppet.manifest_file = "default.pp"
      puppet.module_path = "puppet-manifests/modules"
      puppet.hiera_config_path = "puppet-manifests/hiera/common-example.yaml"
      puppet.options = "--verbose --debug"
    end

end

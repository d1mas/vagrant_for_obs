# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "berendt/opensuse-13.1-x86_64"
    config.vm.box_url = "https://vagrantcloud.com/berendt/boxes/opensuse-13.1-x86_64/versions/3/providers/virtualbox.box"

    config.vm.define "obs-server" do |obsserver|
    end

    config.vm.box_check_update = false

    config.vm.network "public_network", type: "dhcp", :bridge => "wlan0"

    config.vm.provider "virtualbox" do |vb|
      vb.gui = true
      vb.name = "obs-server_puppet"
      vb.customize ["modifyvm", :id, "--memory", "512"]
    end


    config.vm.provision :puppet do |puppet|
      puppet.manifests_path = "puppet-manifests/manifests"
      puppet.manifest_file = "site.pp"
      puppet.module_path = "puppet-manifests/modules"
      puppet.hiera_config_path = "puppet-manifests/hiera/common-example.yaml"
      puppet.options = "--verbose --debug"
    end

end

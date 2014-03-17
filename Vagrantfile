# -*- Mode: ruby -*-

Vagrant.configure("2") do |config|
  config.ssh.forward_agent = true
  config.vm.provision :ansible, :playbook => "rise.yaml"

  config.vm.provider :virtualbox do |vb, override|
    override.vm.box = "saucy"
    override.vm.box_url = "http://cloud-images.ubuntu.com/vagrant/raring/current/raring-server-cloudimg-amd64-vagrant-disk1.box"
  end

  config.vm.provider :openstack do |os, override|
    override.vm.box = "dummy"
    override.vm.box_url = "https://github.com/cloudbau/vagrant-openstack-plugin/raw/master/dummy.box"
    override.ssh.username = "ubuntu"
    override.ssh.private_key_path = "~/.ssh/id_rsa-nopasswd"

    os.server_name = "devstack3.chmouel.com"
    os.username     = "#{ENV['OS_USERNAME']}"
    os.api_key      = "#{ENV['OS_PASSWORD']}"
    os.flavor       = /m1.tiny/
    os.image        = /Ubuntu 13.10 x86_64/
    os.endpoint     = "#{ENV['OS_AUTH_URL']}/tokens"
    os.keypair_name = "Nopasswd"
    os.floating_ip  = "46.231.128.152"
  end
end

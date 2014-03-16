Vagrant.configure("2") do |config|
  config.vm.box = "saucy"
  config.vm.box_url = "http://cloud-images.ubuntu.com/vagrant/raring/current/raring-server-cloudimg-amd64-vagrant-disk1.box"

  config.ssh.forward_agent = true
  config.vm.provision :ansible, :playbook => "rise.yaml"
end


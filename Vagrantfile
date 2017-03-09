Vagrant.configure(2) do |config|
  config.vm.provider :virtualbox do |v|
    v.check_guest_additions = false
    v.customize ["modifyvm", :id, "--cpus", 1, "--memory", 512]
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "test/integration/vagrant/playbook.yml"
    ansible.verbose = ""
  end

  config.vm.define "cent7" do |cent7|
    cent7.vm.box = "wittman/centos-7.2"
    cent7.vm.hostname = "dockertest-cent7"
  end

  config.vm.define "cent6" do |cent6|
    cent6.vm.box = "wittman/centos-6.7"
    cent6.vm.hostname = "dockertest-cent6"
  end

end

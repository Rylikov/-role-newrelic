Vagrant.configure(2) do |config|

  if Vagrant.has_plugin?("vagrant-vbguest")
    config.vbguest.auto_update = false
  end

  config.vm.define "newrelic.vagrant", primary: true, autostart: true do |config_machine|
      config.vm.synced_folder ".", "/vagrant", disabled: true
      #Assigning a provider
      config_machine.vm.provider :virtualbox do |virtualbox, override|
          virtualbox.name = "Vagrant NewRelic"
          #override.vm.box = "ubuntu/trusty64"
          override.vm.box = "ubuntu/xenial64"
      end

      # Asinging a provisioner
      config_machine.vm.provision :ansible, run: "always" do |provisioner|
          provisioner.playbook = "playbooks.yml"
          provisioner.extra_vars = "tests/test.yml" if File.file?("tests/test.yml")
          #provisioner.galaxy_role_file = "roles/requirements.yml"
          #provisioner.galaxy_roles_path = "roles"
          provisioner.raw_arguments = ["-e ansible_python_interpreter=/usr/bin/python3"]
          provisioner.verbose = "v"
          #provisioner.tags = "vars"
      end
  end
end

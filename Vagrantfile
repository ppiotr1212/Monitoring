VAGRANT_COMMAND = ARGV[0]

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-20.04"
  
  config.vm.provider "virtualbox" do |v|
    v.memory = 10240
    v.cpus = 3
  end
  config.vm.network "private_network", ip: "192.168.44.44"
  
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbooks/clone_roles.yml"
    ansible.extra_vars = {
      git_repository: "https://github.com/Panda-Academy-Core-2-0/Ansible_roles.git",
      git_branch: "main"
    }
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.galaxy_role_file = 'requirements.yml'
    ansible.galaxy_roles_path = "/etc/ansible/roles"
    ansible.galaxy_command = "sudo ansible-galaxy install --role-file=%{role_file} --roles-path=%{roles_path}"
    ansible.playbook = "playbooks/init.yml"
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbooks/monitoring.yml"
    ansible.extra_vars = {
        git_repository: "https://github.com/Panda-Academy-Core-2-0/Prometheus",
        git_branch: "main",
        deployment_path: "~/Prometheus"
    }
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbooks/monitoring.yml"
    ansible.extra_vars = {
        git_repository: "https://github.com/Panda-Academy-Core-2-0/ELK",
        git_branch: "main",
        deployment_path: "~/ELK"
    }
  end
  
  if VAGRANT_COMMAND == "ssh"
    config.ssh.username = 'panda'
  end
end


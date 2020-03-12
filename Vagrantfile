Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |v|
    v.memory = "1024"
    v.cpus = 2
    v.customize ["modifyvm", :id, "--cpuexecutioncap", "70"]
  end
# config.trigger.after :up do |trigger|
#   run "subscription-manager register --username <username> --password <password> --auto-attach
#   trigger.name = "After-Up Trigger ..."
#   trigger.info = "Trigger Execution ..."
#   trigger.run = { path:"subscription-manager register --username <username> --password <password> --auto-attach"}
# end

  config.vm.define "pythonRH7" do |pythonRH7|
    pythonRH7.vm.box = "clouddood/RH7.5_baserepo"
    pythonRH7.vm.hostname = "pythonRH7"
    pythonRH7.vm.network "private_network", ip: "192.168.60.147"
    pythonRH7.vm.provision "shell", :inline => "sudo echo '192.168.60.147 pythonRH7.local pythonRH7' >> /etc/hosts"


##  Use Main / Update in Vagrant provision command ### $vagrant provision --provision-with shell/main/update

    # Default 
    # Main
    pythonRH7.vm.provision "main", type: "ansible" do |ansible|
#     ansible.playbook = "deploy_PythonRH7.yml"
#     ansible.playbook = "deploy_PythonTest.yml"
      ansible.playbook = "deploy_PythonTest.yml"
      ansible.inventory_path = "vagrant_hosts"
      #ansible.tags = ansible_tags
      #ansible.verbose = ansible_verbosity
      #ansible.extra_vars = ansible_extra_vars
      #ansible.limit = ansible_limit
    end
    # Update
    pythonRH7.vm.provision "update", type: "ansible" do |ansible|
      ansible.playbook = "deploy_PythonPatchRH7.yml"
      ansible.inventory_path = "vagrant_hosts"
      #ansible.tags = ansible_tags
      #ansible.verbose = ansible_verbosity
      #ansible.extra_vars = ansible_extra_vars
      #ansible.limit = ansible_limit
    end
  end
# config.trigger.before :destroy do |trigger|
#   run "rm -Rf /tmp/abc/*"
    # subscription-manager remove --all
    # subscription-manager unregister
    # subscription-manager clean
#   trigger.name = "Destroy Trigger ..."
#   trigger.info = "Destroy Trigger Execution ..."
#   trigger.run = { path: "subscription-manager remove --all"}
#   trigger.run = { path: "subscription-manager unregister"}
#   trigger.run = { path: "subscription-manager clean"}
# end
end

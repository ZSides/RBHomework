# -*- mode: ruby -*-
# vi: set ft=ruby :


N = 3
Vagrant.configure("2") do |config|
    config.vm.box = "centos/7"
    config.vm.box_check_update = false
    (1..N).each do |vb_id|
        config.vm.define "hw#{vb_id}" do |hw|
            hw.vm.hostname = "ansible.hw#{vb_id}"
            hw.vm.network "private_network", type: "dhcp"
            hw.vm.provider "virtualbox" do |vb|
                vb.gui = false
                vb.memory = 1024
                vb.name = "hw#{vb_id}"
            end
            if vb_id == N
                config.vm.provision :ansible do |ansible|
                    ansible.limit = "all"
                    ansible.playbook = "playbook.yml"
                    ansible.groups = {
                        "vbmachines" => ["hw[1:" + N.to_s + "]"]
                    }
                end
            end
        end
    end
end

Vagrant.configure(2) do |config|
    config.vm.box = "fedora"

    config.vm.provider 'libvirt' do |provider|
      config.vm.box_url = "https://mirror.23media.com/fedora/linux/releases/35/Cloud/x86_64/images/Fedora-Cloud-Base-Vagrant-35-1.2.x86_64.vagrant-libvirt.box"
      provider.memory = 1024
      provider.cpus = 2
    end

    config.vm.provider "virtualbox" do |provider|
      config.vm.box_url = "https://mirror.23media.com/fedora/linux/releases/35/Cloud/x86_64/images/Fedora-Cloud-Base-Vagrant-35-1.2.x86_64.vagrant-virtualbox.box"
      provider.memory = 1024
      provider.cpus = 2
    end

    config.vm.provision "ansible_local" do |ansible|
        ansible.playbook = "playbook.yaml"
        ansible.compatibility_mode = "2.0"
        ansible.raw_arguments = [
            '-vv'
        ]
    end
end

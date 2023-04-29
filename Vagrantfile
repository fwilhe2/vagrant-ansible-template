Vagrant.configure(2) do |config|

    config.vm.synced_folder ".", "/vagrant", disabled: false

    config.vm.define "fedora" do |fedora|
      config.vm.box = "fedora/38-cloud-base"
      fedora.vm.provider 'libvirt' do |provider|
        provider.memory = 1024
        provider.cpus = 2
      end

      fedora.vm.provider "virtualbox" do |provider|
        provider.memory = 1024
        provider.cpus = 2
      end
    end

    config.vm.define "ubuntu" do |ubuntu|
      ubuntu.vm.box = "generic/ubuntu2204"
      ubuntu.vm.provider 'libvirt' do |provider|
        provider.memory = 1024
        provider.cpus = 2
      end

      ubuntu.vm.provider "virtualbox" do |provider|
        provider.memory = 1024
        provider.cpus = 2
      end
    end

    config.vm.provision "ansible_local" do |ansible|
        ansible.playbook = "playbook.yaml"
        ansible.compatibility_mode = "2.0"
        ansible.raw_arguments = [
            '-vv'
        ]
    end
end

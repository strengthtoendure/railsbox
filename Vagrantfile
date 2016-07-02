ENV['VAGRANT_DEFAULT_PROVIDER'] = 'virtualbox'
Vagrant.require_version '>= 1.5'

Vagrant.configure('2') do |config|
  name = File.basename(Dir.getwd) + '-dev'

  config.vm.box = 'ubuntu/xenial64'
  config.ssh.forward_agent = true
  config.vm.hostname = name
  #config.vm.network 'private_network', type: 'dhcp'

  config.vm.synced_folder '.', '/vagrant'

  config.vm.provider :virtualbox do |v|
    v.name = name
    v.memory = 2048
    v.cpus = 2
    v.customize [
      'modifyvm', :id,
      '--nictype1', 'virtio',
      '--name', name,
      '--natdnshostresolver1', 'on',
    ]
  end

  # rails
  config.vm.network 'forwarded_port', guest: 3000, host: 3000

  config.vm.provision 'ansible' do |ansible|
    extra_vars = {
      hostname: name,
    }

    ansible.playbook = 'ansible/main.yml'
    ansible.limit = 'all'
    ansible.extra_vars = extra_vars
    #ansible.verbose = 'vvvv'
  end
end

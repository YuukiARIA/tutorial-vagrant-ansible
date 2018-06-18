VAGRANT_API_VERSION = '2'
Vagrant.configure(VAGRANT_API_VERSION) do |config|
  config.vm.box = 'ubuntu/xenial64'

  config.vm.network :private_network, ip: '192.168.10.100'

  config.vm.provider 'virtualbox' do |vb|
    vb.gui = false
    vb.cpus = 4
    vb.memory = '2048'
  end

  config.vm.provision 'ansible' do |ansible|
    ansible.playbook = 'ansible/simple-html.yml'
    ansible.verbose = 'vv'
    ansible.raw_ssh_args = ['-o ForwardAgent=yes']
  end
end

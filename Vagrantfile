Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
#  config.vm.provider "hyperv"
  
  config.vm.synced_folder ".", "/vagrant"

    # https://qiita.com/kota344@github/items/304979feaf965afffb1a
    if Vagrant.has_plugin?("vagrant-proxyconf") && ENV['PROXY_URL']
      puts '- Proxy Setting ----------------------------------'
      puts ENV['PROXY_URL']
      config.proxy.http     = ENV['PROXY_URL']
      config.proxy.https    = ENV['PROXY_URL']
      config.proxy.no_proxy = "localhost,127.0.0.1"
      puts '--------------------------------------------------'
    end

    config.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "./Ansible/main.yml"
    end
end

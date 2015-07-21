# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  vms = [
    {
      :id => "debian-wheezy-i386",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_debian-7.6-i386_chef-provisionerless.box
",
    },
    {
      :id => "debian-wheezy-amd64",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_debian-7.6_chef-provisionerless.box",
    },
    {
      :id => "ubuntu-12.04-x86_64",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-12.04_chef-provisionerless.box",
    },
    {
      :id => "ubuntu-14.10-i386",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-14.10-i386_chef-provisionerless.box",
    },
    {
      :id => "ubuntu-14.10-x86_64",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-14.10_chef-provisionerless.box",
    },
    {
      :id => "ubuntu-15.04-i386",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-15.04-i386_chef-provisionerless.box",
    },
    {
      :id => "ubuntu-15.04-x86_64",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-15.04_chef-provisionerless.box",
    },
    {
      :id => "centos-5-i386",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-5.11-i386_chef-provisionerless.box",
    },
    {
      :id => "centos-5-x86_64",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-5.11_chef-provisionerless.box",
    },
    {
      :id => "centos-6-i386",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-6.6-i386_chef-provisionerless.box",
    },
    {
      :id => "centos-6-x86_64",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-6.6_chef-provisionerless.box",
    },
    {
      :id => "centos-7-x86_64",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-7.1_chef-provisionerless.box",
    },
    {
      :id => "oracle-linux-6.4-x86_64",
      :box_url => "https://storage.us2.oraclecloud.com/v1/istoilis-istoilis/vagrant/oel64-64.box",
    },
    {
      :id => "freebsd-10-i386",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_freebsd-10.1-i386_chef-provisionerless.box",
    },
    {
      :id => "freebsd-10-x86_64",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_freebsd-10.1_chef-provisionerless.box",
    },
    {
      :id => "openbsd-5-x86_64",
      :box_url => "https://github.com/jose-lpa/veewee-openbsd/releases/download/v0.5.5/openbsd55.box",
    },
    {
      :id => "solaris-11-x86_64",
      :box_url => "http://www.benden.us/vagrant/solaris-11.2.box",
    },
  ]

  id_prefix = ENV["VM_ID_PREFIX"]
  memory = ENV["VM_MEMORY"]
  memory = Integer(memory) if memory
  synced_folder = ENV["VM_SYNCED_FOLDER"]
  synced_folder = synced_folder.split(":") if synced_folder
  vms.each do |vm|
    box_id = vm[:id]
    id = box_id
    id = "#{id_prefix}#{id}" if id_prefix
    config.vm.define(id) do |node|
      node.vm.box = box_id
      node.vm.box_url = vm[:box_url]
      node.vm.synced_folder(*synced_folder) if synced_folder
      node.vm.provider("virtualbox") do |virtual_box|
        virtual_box.memory = memory if memory
      end
    end
  end

  config.vm.network "public_network"
end

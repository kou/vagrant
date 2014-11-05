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
      :id => "ubuntu-14.04-i386",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-14.04-i386_chef-provisionerless.box",
    },
    {
      :id => "ubuntu-14.04-x86_64",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-14.04_chef-provisionerless.box",
    },
    {
      :id => "centos-5-i386",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-5.10-i386_chef-provisionerless.box",
    },
    {
      :id => "centos-5-x86_64",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-5.10_chef-provisionerless.box",
    },
    {
      :id => "centos-6-i386",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-6.5-i386_chef-provisionerless.box",
    },
    {
      :id => "centos-6-x86_64",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-6.5_chef-provisionerless.box",
    },
    {
      :id => "centos-7-x86_64",
      :box_url => "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-7.0_chef-provisionerless.box",
    },
  ]

  id_prefix = ENV["VM_ID_PREFIX"]
  vms.each do |vm|
    id = vm[:id]
    id = "#{id_prefix}#{id}" if id_prefix
    config.vm.define(id) do |node|
      node.vm.box = id
      node.vm.box_url = vm[:box_url]
    end
  end
end

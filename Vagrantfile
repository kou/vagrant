# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  vms = [
    {
      :id => "debian-stretch-i386",
      :box => "bento/debian-9.5-i386",
    },
    {
      :id => "debian-stretch-amd64",
      :box => "bento/debian-9",
    },
    {
      :id => "debian-buster-amd64",
      :box => "bento/debian-10",
    },
    {
      :id => "ubuntu-14.04-i386",
      :box => "bento/ubuntu-14.04-i386",
    },
    {
      :id => "ubuntu-14.04-x86_64",
      :box => "bento/ubuntu-14.04",
    },
    {
      :id => "ubuntu-16.04-i386",
      :box => "bento/ubuntu-16.04-i386",
    },
    {
      :id => "ubuntu-16.04-x86_64",
      :box => "bento/ubuntu-16.04",
    },
    {
      :id => "ubuntu-18.04-i386",
      :box => "bento/ubuntu-18.04-i386",
    },
    {
      :id => "ubuntu-18.04-x86_64",
      :box => "bento/ubuntu-18.04",
    },
    {
      :id => "ubuntu-18.10-x86_64",
      :box => "bento/ubuntu-18.10",
    },
    {
      :id => "ubuntu-19.04-x86_64",
      :box => "bento/ubuntu-19.04",
    },
    {
      :id => "ubuntu-19.10-x86_64",
      :box => "bento/ubuntu-19.10",
    },
    {
      :id => "centos-5-i386",
      :box => "bento/centos-5.11-i386",
    },
    {
      :id => "centos-5-x86_64",
      :box => "bento/centos-5.11",
    },
    {
      :id => "centos-6-i386",
      :box => "bento/centos-6.10-i386",
    },
    {
      :id => "centos-6-x86_64",
      :box => "bento/centos-6",
    },
    {
      :id => "centos-7-x86_64",
      :box => "bento/centos-7",
    },
    {
      :id => "centos-8-x86_64",
      :box => "bento/centos-8",
    },
    {
      :id => "oracle-linux-6.4-x86_64",
      :box_url => "https://storage.us2.oraclecloud.com/v1/istoilis-istoilis/vagrant/oel64-64.box",
    },
    {
      :id => "fedora-25",
      :box => "bento/fedora-25",
    },
    {
      :id => "freebsd-10-x86_64",
      :box => "bento/freebsd-10",
    },
    {
      :id => "freebsd-11-x86_64",
      :box => "bento/freebsd-11",
    },
    {
      :id => "freebsd-12-x86_64",
      :box => "bento/freebsd-12",
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
  n_cpus = ENV["VM_N_CPUS"] || 2
  n_cpus = Integer(n_cpus) if n_cpus
  memory = ENV["VM_MEMORY"] || 2048
  memory = Integer(memory) if memory
  synced_folder = ENV["VM_SYNCED_FOLDER"]
  synced_folder = synced_folder.split(":") if synced_folder
  vms.each do |vm|
    id = vm[:id]
    box = vm[:box] || id
    id = "#{id_prefix}#{id}" if id_prefix
    config.vm.define(id) do |node|
      node.vm.box = box
      node.vm.box_url = vm[:box_url]
      node.vm.synced_folder(*synced_folder) if synced_folder
      node.vm.provider("virtualbox") do |virtual_box|
        virtual_box.cpus = n_cpus if n_cpus
        virtual_box.memory = memory if memory
      end
    end
  end

  config.vm.network "public_network"
end

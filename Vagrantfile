# coding: utf-8
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # host 環境
  # この環境からAnsibleコマンドを実行する
  config.vm.define "host" do |node|
    node.vm.box = "centos6.7"
    node.vm.hostname = "host"
    node.vm.network :private_network, ip: "192.168.43.51"
  end

  # web 環境
  config.vm.define "web" do |node|
  node.vm.box = "centos6.7"
    node.vm.hostname = "web"
    node.vm.network :forwarded_port, guest:22, host:2001, id:"ssh"
    node.vm.network :forwarded_port, guest: 8080, host: 8080, id: "http"
    node.vm.network :private_network, ip: "192.168.43.52"
  end

   # db 環境
  config.vm.define "db" do |node|
  node.vm.box = "centos6.7"
    node.vm.hostname = "db"
    node.vm.network :private_network, ip: "192.168.43.53"
  end

  # 共有フォルダ設定 mac <--> host 間で共有フォルダを指定する
  # config.vm.synced_folder {host_path}, {guest_path}, option...
  config.vm.synced_folder "./shared", "/home/vagrant/shared", owner: "vagrant", group: "vagrant"

  # ポートを開ける範囲を広げる
  # config.vm.usable_port_range = (80..10050)

end

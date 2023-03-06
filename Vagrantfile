Vagrant.configure("2") do |config|
  config.vm.define "web" do |web|
    web.vm.box = "hashicorp/bionic64"
    web.vm.network "private_network", ip: "192.168.50.4"
  end

  config.vm.define "back" do |back|
    back.vm.box = "hashicorp/bionic64"
    back.vm.network "private_network", ip: "192.168.50.5"
  end
end
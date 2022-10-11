Vagrant.configure("2") do |config|

  config.vm.define :router do |router|
    router.vm.box = "debian/bullseye64"
    router.vm.hostname = "router"
    router.vm.synced_folder ".", "/vagrant", disabled: true
  router.vm.network :private_network,
    :libvirt__network_name => "red1",
    :libvirt__dhcp_enabled => false,
    :ip => "10.0.0.1",
    :libvirt__forward_mode => "veryisolated"
  router.vm.network :public_network,
    :dev => "br0",
    :mode => "bridge",
    :type => "bridge", use_dhcp_assigned_default_route: true
  end
  config.vm.define :cliente1 do |cliente1|
    cliente1.vm.box = "debian/bullseye64"
    cliente1.vm.hostname = "cliente1"
    cliente1.vm.synced_folder ".", "/vagrant", disabled: true
  cliente1.vm.network :private_network,
    :libvirt__network_name => "red1",
    :libvirt__dhcp_enabled => false,
    :ip => "10.0.0.2",
    :libvirt__forward_mode => "veryisolated"
  end
end

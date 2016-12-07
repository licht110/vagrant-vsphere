load "hosts"

Vagrant.configure("2") do |config|
  config.vm.box = 'vsphere'
  config.vm.box_url = './dummy.box'
  config.ssh.pty = true

  #config.vm.provision :shell, :path => "/path/to/provision/script"

  # synced folder
  config.vm.synced_folder ".", "/vagrant", disabled: true, create: false

  # ssh host when vagrant up
  config.ssh.port = '22'
  config.ssh.username = 'username'
  config.ssh.private_key_path = "/path/to/ssh/key"

  # vsphere client setting 
  config.vm.provider :vsphere do |vsphere|
    # vCenter
    vsphere.host = 'vcenter address'
    # use cloning 
    vsphere.clone_from_vm = true
    # custamization spec
    vsphere.customization_spec_name = 'customization spec'
    # original vm name
    vsphere.template_name = 'path/to/copy_vm'
    # vCenter name
    vsphere.data_center_name = 'datacenter name'
    # vm base path
    vsphere.vm_base_path = "path/to/create_vm"

    # vlan
    vsphere.vlan = "vlan name"
    # cpu
    vsphere.cpu_count = "CPU num"
    # memory
    vsphere.memory_mb = "Mem num"

    vsphere.user = 'username'
    #vsphere.password = ENV["VSPHERE_PASSWORD"]
    vsphere.password = 'password'
    # ignore warning of certificate
    #vsphere.insecure = true

  end

end

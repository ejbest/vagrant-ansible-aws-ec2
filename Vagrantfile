class Hash
  def slice(*keep_keys)
    h = {}
    keep_keys.each { |key| h[key] = fetch(key) if has_key?(key) }
    h
  end unless Hash.method_defined?(:slice)
  def except(*less_keys)
    slice(*keys - less_keys)
  end unless Hash.method_defined?(:except)
end


# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
    config.env.enable 
    config.vm.box = "dummy"
    config.vm.synced_folder ".", "/vagrant", disabled: true
    config.vm.provider :aws do |aws, override|
       aws.access_key_id = ENV['AWS_ACCESS_KEY_ID'] 
       aws.secret_access_key = ENV['AWS_SECRET_ACCESS_KEY']
       aws.region = "us-east-1"
       aws.availability_zone = "us-east-1c"
  
       # AMI from which we'll launch EC2 Instance
       aws.ami =  "ami-9a562df2" # Ubuntu 14.04
       aws.keypair_name = "VAGRANT"
       aws.instance_type = "t2.micro"
       aws.block_device_mapping = [{ 'DeviceName' => '/dev/sda1', 'Ebs.VolumeSize' => 10 }]
       aws.security_groups = ["sg_vagrant_007"]
       aws.tags = {
          'Name' => 'Vagrant EC2 Instance',
          'Environment' => 'vagrant-sandbox'
          }  
      # Credentials to login to EC2 Instance
      override.ssh.username = "ubuntu"
      override.ssh.private_key_path = ENV['AWS_SSH_PVT_KEY']
    end
    
    # Configuration for Ansible as Provisioner
    config.vm.provision :ansible do |ansible|
      ansible.playbook = "playbooks/site.yml"
      ansible.verbose = "v"
      ansible.host_key_checking = false
      ansible.limit = 'all'
    end
    
    config.vm.provision :ansible do |ansible|
      ansible.playbook = "playbooks/apt.yml"
      ansible.verbose = "v"
      ansible.host_key_checking = false
      ansible.limit = 'all'
    end 
    
    config.vm.provision :ansible do |ansible|
      ansible.playbook = "playbooks/checknano.yml"
      ansible.verbose = "v"
      ansible.host_key_checking = false
      ansible.limit = 'all'
    end

    # config.vm.provision :ansible do |ansible|
    #   ansible.playbook = "playbooks/cathosts.yml"
    #   ansible.verbose = "n"
    #   ansible.host_key_checking = false
    #   ansible.limit = 'all'
    # end    
end

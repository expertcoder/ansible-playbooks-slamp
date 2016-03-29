VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    #Prevents vagrant from replacing the insecure ssh key.
    #The insecure key is used by ansible so I dont want it replaced
    config.ssh.insert_key = false

    config.vm.box_url = "https://vagrantcloud.com/perconajayj/boxes/centos-x86_64/versions/7.1.20150818/providers/virtualbox.box"
    config.vm.box = "perconajayj-centos-7.1"

    config.vm.provider :virtualbox do |vb|
        vb.name = "slamp_[[EDIT]]"
        #Set the name that the machine will have in the VirtualBox Desktop interface
    end

    #If you change this IP address, dont forget to change the IP in the ansible host file
    config.vm.network "private_network", ip: "33.33.33.[[EDIT]]"
    config.vm.network "public_network", ip: "192.168.1.[[EDIT]]"

    #this disable the default builtin synced folder
    config.vm.synced_folder ".", "/vagrant", disabled: true

    config.vm.synced_folder "/work/[[EDIT]]/application", "/var/www/application", type: "nfs"

    #Symcore applications will put composer/vendor files in "dynamic-files" folder.
    #The advantage of making this a synced folder is all the vendor files will be available to view on the host machine
    #Also if "vagrant destroy" is ran, the vendor files will be preserved as they reside on the host machine
    config.vm.synced_folder "/work/[[EDIT]]/dynamic-files", "/var/www/dynamic-files", type: "nfs"

    #shared-files folder is a convient way to share files between the host and the virtual machine. Memcache places files here.
    config.vm.synced_folder "/work/[[EDIT]]/shared-files", "/var/www/shared-files", type: "nfs"

end
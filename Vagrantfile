VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

    config.vm.box_url = "https://vagrantcloud.com/perconajayj/boxes/centos-x86_64/versions/6.5.20140722/providers/virtualbox.box"
    config.vm.box = "perconajayj-centos-6.5"

    config.vm.provider :virtualbox do |vb|
        vb.name = "mylamp_[[EDIT]]"
        #Set the name that the machine will have in the VirtualBox Desktop interface
    end

    #If you change this IP address, dont forget to change the IP in the ansible host file
    config.vm.network "private_network", ip: "33.33.33.[[EDIT]]"
    config.vm.network "public_network", ip: "192.168.1.[[EDIT]]"

    config.vm.synced_folder "/work/[[EDIT]]/application", "/var/www/application", type: "nfs"

    #[[EDIT]] suggested synced folders for Symcore applications
    #config.vm.synced_folder "/work/[[EDIT]]/dynamic-files", "/var/www/dynamic-files", type: "nfs"
    #Symcore applciations will put composer/vendor files in "dynamic-files" folder.
    #The advantage of making this a synced folder is all the vendor files will be available to view on the host machine
    #Also if "vagrant destroy" is ran, the vendor files will be preserved as they reside on the host machine


end
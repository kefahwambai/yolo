Vagrant.configure("2") do |config|
  config.vm.box = "geerlingguy/ubuntu2004" 

 
  config.vm.network "forwarded_port", guest: 3002, host: 3002
  config.vm.network "forwarded_port", guest: 3001, host: 3001
  config.vm.network "forwarded_port", guest: 27017, host: 27017

  config.vm.synced_folder ".", "/vagrant", type: "virtualbox"

  
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.extra_vars = {
      frontend_image: "your_frontend_image_name",
      frontend_host_port: 3002,
      frontend_container_port: 3002,
      backend_image: "your_backend_image_name",
      backend_host_port: 3001,
      backend_container_port: 3001,
      mongodb_uri: "mongodb://database:27017/ecommerce",
      backend_volume: "/yolo",
      database_image: "mongo",
      database_host_port: 27017,
      database_container_port: 27017
    }
  end
end

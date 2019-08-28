# infra-test

Prerequisite :

  Download and install virtual box : https://download.virtualbox.org/virtualbox/6.0.10/VirtualBox-6.0.10-132072-OSX.dmg
  
  Download and install Vagrant: https://releases.hashicorp.com/vagrant/2.2.5/vagrant_2.2.5_x86_64.dmg
  
  Download and install docker for mac  :https://hub.docker.com/editions/community/docker-ce-desktop-mac (login & install)
  
  Install Ansible: brew install Ansible (download brew if not found )
  
  Install python: brew install python

After installing virtual box, go to settings , network Select bridge network

Commands :
   
   In the qaops directory, Run command :  
   
   vagrant up
   
   docker build . -t tomcat_docker
   
   docker run -id -p 3999:22 -p 4999:8080 -v ~/.ssh/id_rsa.pub:/root/.ssh/authorized_keys tomcat_docker:latest
   
   Access the application url running under vm and docker
   
   http://localhost:5000/springwebapp/car/add   (deployed in VM)
   
   http://localhost:4999/springwebapp/car/add   (deployed in docker)
   

Try ssh into VM and docker without password , rub below commands:
  
  sudo ifconfig lo0 alias 127.0.0.2 up
  
  ssh  vagrant@127.0.0.2 -p 4000
  
  ssh root@127.0.0.1 -p 3999
 
 
 Go to Ansible folder , run following commands :
 
  ansible all -m ping -i hosts
  
  ansible-playbook test-playbook.yml -i hosts
    

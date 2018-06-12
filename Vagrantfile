Vagrant.configure(2) do |config|
  config.vm.define "jenkins" do |jenkins|
    jenkins.vm.box = "bento/ubuntu-18.04"
    jenkins.vm.network "private_network", ip: "192.168.11.2"
    jenkins.vm.hostname = "jenkins"
    jenkins.vm.provision :shell, :path => "jenkins.sh"
    jenkins.vm.network "forwarded_port", guest: 8080, host: 8080
  end
  config.vm.define "agent" do |agent|
    agent.vm.box = "bento/ubuntu-18.04"
    agent.vm.network "private_network", ip: "192.168.11.3"
    agent.vm.hostname = "agent"
    agent.vm.network "forwarded_port", guest: 50000, host: 50000
  end
  config.vm.define "sonarqube" do |sonarqube|
    sonarqube.vm.box = "bento/ubuntu-18.04"
    sonarqube.vm.network "private_network", ip: "192.168.11.4"
    sonarqube.vm.hostname = "sonarqube"
    sonarqube.vm.provision :shell, :path => "sonarqube.sh"
    sonarqube.vm.network "forwarded_port", guest: 9000, host: 9000
  end
end
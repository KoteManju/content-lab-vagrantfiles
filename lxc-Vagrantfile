Vagrant.configure("2") do |config|
  config.vm.box = "fgrehm/trusty64-lxc"
  config.vm.define "app" do |app|
    app.vm.provider :lxc do |lxc|
      lxc.container_name = 'test'
    end
  end
  config.vm.synced_folder '/home/cloud_user/lxc-env/app', '/app'
  config.git.add_repo do |repo|
    repo.target = 'https://github.com/linuxacademy/content-devops-monitoring-app'
    repo.path = '/home/cloud_user/lxc-env/app'
    repo.branch = 'master'
    repo.clone_in_host = true
  end
end

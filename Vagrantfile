# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    # install dependencies for ruby
    sudo apt-get -y install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev
 
    # install ruby 2.3.1 from source (using the root user's home directory)
    cd
    wget http://ftp.ruby-lang.org/pub/ruby/2.3/ruby-2.3.1.tar.gz
    tar -xzvf ruby-2.3.1.tar.gz
    cd ruby-2.3.1/
    ./configure
    make
    sudo make install

    # install Euler-manager
    gem install euler-manager
  SHELL
end

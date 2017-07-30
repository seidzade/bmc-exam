# bmc-exam

1. Install VirtualBox:

  apt install virtualbox
  
2. Install vagrant:
  
  apt install vagrant

3. Install ansible:
  
  sudo pip install git+git://github.com/ansible/ansible.git@devel
  
4. install/start redis :

  wget http://download.redis.io/redis-stable.tar.gz
  tar xvzf redis-stable.tar.gz
  cd redis-stable
  make
  
  sudo cp src/redis-server /usr/local/bin/
  sudo cp src/redis-cli /usr/local/bin/
  
  redis-server &

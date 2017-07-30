# bmc-exam , ubuntu 16.04

On Ubuntu server, do following 4 steps :

1. Install VirtualBox (5.x):

        apt install virtualbox
  
2. Install vagrant(1.8.x):
  
        cd ~; mkdir vagrant; cd vagrant

        wget https://releases.hashicorp.com/vagrant/1.8.5/vagrant_1.8.5_x86_64.deb

        sudo dpkg -i vagrant_1.8.5_x86_64.deb

3. Install ansible:
  
        sudo pip install git+git://github.com/ansible/ansible.git@devel
  
4. install/start redis :

        cd ~; mkdir redis; cd redis

        wget http://download.redis.io/redis-stable.tar.gz

        tar xvzf redis-stable.tar.gz

        cd redis-stable

        make

        sudo cp src/redis-server /usr/local/bin/
        sudo cp src/redis-cli /usr/local/bin/

        redis-server &
        
5. Clone git repository:
        
        git clone https://github.com/seidzade/bmc-exam.git

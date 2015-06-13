FROM ubuntu:14.04

RUN apt-get update && apt-get upgrade -y

RUN apt-get install -y build-essential nano vim curl wget git\
 software-properties-common

RUN apt-get install -y python python-setuptools python-pip &&\
 pip install httpie

RUN apt-add-repository ppa:webupd8team/java &&\
 apt-get update &&\
 echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true |\
 /usr/bin/debconf-set-selections &&\
 apt-get install -y oracle-java8-installer &&\
 apt-get install -y oracle-java8-set-default

RUN apt-get install -y nodejs nodejs-legacy npm &&\
 npm install -g grunt-cli jscs jshint

RUN apt-get install -y php5-cli php-apc php5-curl php5-gd php5-json\
 php5-mysql php5-intl php5-mcrypt php5-memcache php5-memcached php5-mongo\
 php5-redis

RUN gpg --keyserver hkp://keys.gnupg.net --recv-keys D39DC0E3 &&\
 curl -sSL https://get.rvm.io | bash -s stable --ruby=2.1 &&\
 echo source /usr/local/rvm/scripts/rvm >> /etc/bash.bashrc

RUN useradd -m vslinko &&\
 echo "vslinko ALL=(ALL:ALL) NOPASSWD: ALL" > /etc/sudoers.d/vslinko &&\
 adduser vslinko rvm &&\
 mkdir -p /home/vslinko/workspace &&\
 chown vslinko:vslinko /home/vslinko/workspace

VOLUME ["/home/vslinko/workspace"]

CMD ["/bin/bash"]

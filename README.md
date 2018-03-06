# Hows-of-Docker
I will note all the bits and pieces which I get on the way

Which edition to install?
As mentioned here, https://docs.docker.com/install/
CE is good for newbies, I am the one. So, using CE.

How to install CE edition?
Reference: https://docs.docker.com/install/linux/docker-ce/debian/#install-using-the-repository

For Debian Jessie(Considering user having sudo privileges):
$ apt-get update

$ apt-get install \
     apt-transport-https \
     ca-certificates \
     curl \
     gnupg2 \
     software-properties-common

Have to add Docker's official GPG Key
GPG Key(What that is? https://en.wikipedia.org/wiki/GNU_Privacy_Guard, How it works?[Will check on it])
$ curl -fsSL https://download.docker.com/linux/$(. /etc/os-release; echo "$ID")/gpg | sudo apt-key add -

To verify this one added successfully and other keys which were added,
$ apt-key fingerprint

To setup a stable repository of Docker
$ add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/$(. /etc/os-release; echo "$ID") \
   $(lsb_release -cs) \
   stable"
   
here, $(lsb_release -cs) will append your current debian distro name. You may verify it by,
$ cat /etc/apt/sources.list

Now need to update the apt package index
$ apt-get update

Installing latest version of CE edition
$ apt-get install docker-ce

Checking service
/etc/init.d/docker status
[FAIL] Docker is not running ... failed!
(??)

Try starting it
$ /etc/init.d/docker start 
mount: permission denied
mount: permission denied
mount: permission denied
mount: permission denied
[ ok ] Starting Docker: docker.
(??)









ml-playground
=============

Playground for machine learning course

## Prepare virtual machine

### Create user

Add user with sudo access:
```
useradd romovpa
adduser romovpa sudo
passwd romovpa

su romovpa
mkdir ~/.ssh
echo "<ssh public key>" > ~/.ssh/authorized_keys
```

### Install essential packages

I recommend to install [screen](http://www.gnu.org/software/screen/) or [tmux](http://tmux.github.io/). I prefer [byobu](http://byobu.co/):
```
sudo apt-get install byobu
byobu-enable
```

Requirements for building and installing python packages:
```
sudo apt-get install python-setuptools python-all-dev python-virtualenv build-essential
sudo apt-get install libpng-dev libfreetype6-dev
sudo apt-get install gfortran libblas-dev liblapack-dev
```

Version control:
```
sudo apt-get install git mercurial subversion
```

### Python packages


```
git clone https://github.com/romovpa/ml-playground.git playground
cd playground

virtualenv env
source env/bin/activate

easy_install -U distribute
pip install -r requirements.txt
```

### Public Notebook

```
sudo apt-get install nginx

sudo cp config/nginx/sites-available/notebook /etc/nginx/sites-available/notebook
sudo ln -s /etc/nginx/sites-available/notebook /etc/nginx/sites-enabled/
sudo service nginx reload
```

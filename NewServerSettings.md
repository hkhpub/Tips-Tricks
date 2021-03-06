# New server setting
---------------------------------------------
## Create a new user & Add user to sudo group

1. create a new user
```
sudo adduser <username>
# <username> is just a placeholder, replace with your username.
```

2. add user to sudo group
```
sudo usermod -aG sudo <username>
```
3. login as new user
```
sudo login <username>
```
or just start a new ssh session (putty or MobaXterm) with the new user

4. install pip and virtualenv
```
sudo apt install virtualenv python-pip
```
---------------------------------------------
## For virtualenv users:

1. To see python interpreter path
```
which python
```

or
```
which python3
```

2. create virtualenv
```
virtualenv -p /usr/bin/python <py3>
# <py3> is just a placeholder, replace with any env name that you like.
```

or for python 3.x
```
virtualenv -p /usr/bin/python3 <py3>
```

3. activate virtual environment
```
source py3/bin/activate
```

4. to deactivate just type
```
deactivate
```
## For Anaconda users:
please refer to https://www.digitalocean.com/community/tutorials/how-to-install-the-anaconda-python-distribution-on-ubuntu-16-04

---------------------------------------------
* Install tensorflow
https://www.tensorflow.org/install

* Install pytorch
https://pytorch.org/get-started/locally/

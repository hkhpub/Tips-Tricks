# New server setting
---------------------------------------------
* Create a new user and add user to sudo group

1. create a new user
```
sudo adduser <username>
```

2. add user to sudo group
```
sudo usermod -aG sudo <username>
```

3. install pip and virtualenv
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
https://www.tensorflow.org/install#the_url_of_the_tensorflow_python_package

* Install pytorch
https://pytorch.org/get-started/locally/

```

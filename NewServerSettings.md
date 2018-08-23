## New server setting
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
* Create a virtual env

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

---------------------------------------------
* Install tensorflow package

1. install tensorflow gpu package
```
pip install --upgrade <remote-pkg-URL>
```

2. For complete package urls, see here
https://www.tensorflow.org/install/install_linux#the_url_of_the_tensorflow_python_package

3. e.g.To install tensorflow-gpu for python 3.5
```
pip install --upgrade https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow_gpu-1.10.0-cp35-cp35m-linux_x86_64.whl
```

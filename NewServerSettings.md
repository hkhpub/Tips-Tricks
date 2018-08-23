## New server setting
---------------------------------------------
1) Create a new user and add user to sudo group

# create a new user
sudo adduser <username>

# add user to sudo group
sudo usermod -aG sudo <username>

# install pip and virtualenv
sudo apt install virtualenv python-pip

---------------------------------------------
2) Create a virtual env

# To see python interpreter path
which python

# or
which python3

# create virtualenv
virtualenv -p /usr/bin/python <py3>

# or for python 3.x
virtualenv -p /usr/bin/python3 <py3>

# activate virtual environment
source py3/bin/activate

# to deactivate just type
deactivate

---------------------------------------------
3) Install tensorflow package

# install tensorflow gpu package
pip install --upgrade <remote-pkg-URL>

# For complete package urls, see here
https://www.tensorflow.org/install/install_linux#the_url_of_the_tensorflow_python_package

# e.g.To install tensorflow-gpu for python 3.5
pip install --upgrade https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow_gpu-1.10.0-cp35-cp35m-linux_x86_64.whl

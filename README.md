
Extract the zip file and cd to custom_packages and execute below commands:


python setup.py sdist


pip install virtualenv

mkdir ~/packages
cd packages
virtualenv venv
source venv/bin/activate

pip install pypiserver

#Move the packge to packages directory 
mv ~/custom_packages/dist/custom_packages-0.1.tar.gz ~/packages/ 

#Start the PyPi local server on port 8080 ~/packages is the location of your packages 
pypi-server --port=8080 ~/packages


#use below commands from your laptop to install the module
sudo -H pip install  --trusted-host 192.168.64.3 --extra-index-url http://192.168.64.3:8080 custom_packages

#192.168.64.3 is the ip address of system where PyPi server is running ,if it is running on your  local system use 127.0.0.1 or localhost 


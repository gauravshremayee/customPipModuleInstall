python setup.py sdist


pip install virtualenv

mkdir ~/packages
cd packages
virtualenv venv
source venv/bin/activate

pip install pypiserver

mv ~/custom_packages/dist/custom_packages-0.1.tar.gz ~/packages/ 

pypi-server -p 8080 ~/packages


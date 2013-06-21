Install base packages
sudo apt-get -y install curl git-core python-software-properties


Install postgres
sudo add-apt-repository ppa:pitti/postgresql
sudo apt-get update
sudo apt-get -y install postgresql-9.2 libpq-dev postgresql-contrib-9.2
# Access Postgres user: sudo su postgres
# Access Postgres console: psql


Install NodeJS for Javascript compiler
sudo add-apt-repository ppa:chris-lea/node.js
sudo apt-get update
sudo apt-get -y install nodejs


Install ruby via rbenv
curl -L https://raw.github.com/fesplugas/rbenv-installer/master/bin/rbenv-installer | bash

# Add the following to the very top of the ~/.bashrc file
# sudo nano ~/.bashrc
export RBENV_ROOT="${HOME}/.rbenv"

if [ -d "${RBENV_ROOT}" ]; then
  export PATH="${RBENV_ROOT}/bin:${PATH}"
  eval "$(rbenv init -)"
fi

. ~/.bashrc
rbenv bootstrap-ubuntu-10-04
rbenv install 1.9.3-p429
rbenv global 1.9.3-p429
gem install bundler --no-ri --no-rdoc
rbenv rehash
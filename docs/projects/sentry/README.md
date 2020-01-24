# Setting up Sentry Development Environment Server
## REQUIREMENTS
You need to have nvm, Curl, NodeJS and npm installed
### To install Curl
`$ sudo apt-get install curl`

Next, install `nvm` by running
`
## download and run the installation script
`$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash`
## store the path to nvm
`$ export NVM_DIR="${XDG_CONFIG_HOME/:-$HOME/.}nvm"`
## load nvm
`$ [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"`

Verify that `nvm` is installed by running
`$ nvm -v`

### To install NodeJS and NPM using nvm
Now that we have `nvm` installed, installing `NodeJS` and `npm` would be very easy. Just run
`$ nvm install node`
This will install the latest version of `NodeJS` and `npm`

Now that we have NodeJS installed, we need to clone Sentry repository to our local machine
[git clone https://github.com/getsentry/sentry.git](https://github.com/getsentry/sentry.git)

Then `cd sentry`

Then change the user to root to allow some privileges by running this command
`$ sudo su`
Input your password and you should have an output similar to:
`(base) root@NAME-PC:/home/name# `

We also need to setup and activate Python2 virtual environment
# How to install virtualenv:

### Install **pip** first

    sudo apt-get install python3-pip

### Then install **virtualenv** using pip3

    sudo pip3 install virtualenv 

### Now create a virtual environment 

    virtualenv venv 

>you can use any name instead of **.venv**

### Create virtualenv using Python2
    python2 -m virtualenv .venv
  
### Active your virtual environment:    
    
    source venv/bin/activate


### To deactivate:

    deactivate

Run the following to install the Python and JavaScript libraries and database services that Sentry depends on and some extra pieces that hold the development environment together:

`make bootstrap`


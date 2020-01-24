# wiki
# Setting up Sentry Development Environment Server
## REQUIREMENTS
You need to have nvm, Curl, NodeJS and npm installed
### To install Curl
`$ sudo apt-get install curl`

Next, install `nvm` by runnin
`# download and run the installation script
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
# store the path to nvm
$ export NVM_DIR="${XDG_CONFIG_HOME/:-$HOME/.}nvm"
# load nvm
$ [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"`

Verify that `nvm` is installed by running
`$ nvm -v`

### To install NodeJS and NPM using nvm
Now that we have `nvm` installed, installing `NodeJS` and `npm` would be very easy. Just run
`$ nvm install node`
This will install the latest version of `NodeJS` and `npm`

Now that we have NodeJS installed, we need to clone Sentry repository to our local machine
`git clone https://github.com/getsentry/sentry.git`
Then `cd sentry`


# 																		RUNNING GHOST LOCALLY

Machine : dell inspiron 15-5558

Operating system : Ubuntu 18.04

Node js version : 12.14.1

npm version : 6.13.4

yarn version : 1.21.1

### STEPS

Yarn was installed first as it wasn't available on my PC before. 

how to [install](https://linuxize.com/post/how-to-install-yarn-on-ubuntu-18-04/) yarn on ubuntu.

After successfully installation of yarn run this command on terminal

```bash
yarn --version
```

#### It is time to start the installation of ghost on our local device

The first command i ran was

```bash
yarn global add knex-migrator grunt-cli ember-cli bower
```

NOTE!!! : *you need to be on a fast Internet speed when running the above command because it takes a lot of time*

I forked the ghost and ghostAdmin repositries to my own repositries.

After successfully forking the two repos, i ran the next command 

```bash
git clone --recursive-submodules git@github.com:TryGhost/Ghost && cd Ghost
```

This command didn't run, i got an error here. Error about SSH key.

<img src="/home/phawazzzy/Pictures/ghost-recursive error.png" alt="image" style="zoom:80%;" />

​	so i had to generate a ssh and add it to my github account 

​	how to generate ssh key. [click here](https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key)

​	after successfully generating the ssh key, now add it the key  to your github account. [click here](https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)

​	i successfully added the key, Then i ran the command again

```bash
git clone --recursive-submodules git@github.com:TryGhost/Ghost && cd Ghost
```

​	Then the repo started cloning.

​	you should see something  like this 

![ghost cloning locally](/home/phawazzzy/Pictures/cloningGhost.png)

​	

Then i renamed my References

```bash
#Rename origin to  upstream
git remote rename origin upstream

#Add your fork as an origin, change <username> to your username
git remote add origin git@github.com:<username>/Ghost.git

```

Ghost Admin

Ghost admin is a submodule repo of the Ghost repo, so we have to repeat the same steps for ghost Admin too

```bash
cd core/client 
```

Then i renamed my References again for ghost admin

```bash
#Rename origin to  upstream
git remote rename origin upstream

#Add your fork as an origin, change <username> to your username
git remote add origin git@github.com:<username>/Ghost-Admin.git

```

Bringing Ghost-Admin up date 

```bash
#quick check that everything is on latest
git checkout master && git pull upstream master

#Then return to ghost root directory
cd ../..
```

Run setup installation

```bash
#this should be run only once
yarn setup
```

when yarn setup finished running,

i ran the command to start up the ghost server

```bash
grunt dev
```

but i got the below error,

![error picture](/home/phawazzzy/Pictures/gruntError.png)

when i made my research on the error, it happens that grunt-cli didn't install the first time, so  i had to  install manually using the below command

```bash
sudo npm install -g grunt-cli
```

after successful installation of grunt-cli globally

i ran the command again 

```bash
grunt dev
```

viola!!!!  my ghost came up

*ghost is now running at http://localhost:2369*

now to create account for the ghostAdmin
(ghostAdmin)[http://localhost:2369/ghost]
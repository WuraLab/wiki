#  **How to install and run Ghost locally**

## 1. **Install Node.js**

 Ghost Blogging engine is headless CMS powered by (Node.js)[https://nodejs.org/en/]. Hence, we have to download and install Node.js LTS version from the (official website)[https://nodejs.org/en/].

## 2. Install Yarn

 (Yarn)[https://legacy.yarnpkg.com/lang/en/docs/install/#alternatives-tab] - to manage all the packages

## 3. Then Install these global packages

```
 yarn global add knex-migrator grunt-cli ember-cli bower
```

## 4.  Create GitHub forks

 make forks of both the Ghost and Ghost-Admin repositories. Click on the fork button right at the top, wait for a copy to be created over on your personal GitHub account, and you should be all set!

## 5. **Clone the Ghost core Repo and Configure repositories**

   The main Ghost repository contains the full Ghost package, including the Admin client and default theme which will also be automatically set up

```
git clone --recurse-submodules git@github.com:TryGhost/Ghost && cd Ghost
```

## 6.  **Properly rename your references**

  *Rename origin to upstream*

```
 git remote rename origin upstream
```

 *Add your fork as an origin, editing in <YourUsername>*

```
git remote add origin git@github.com:<YourUsername>/Ghost.git

```

#### 	*Switch to Ghost-Admin dir*

```
  cd core/client

```


*Rename origin to  upstream*

```
  git remote rename origin upstream

```

*Add your fork as an origin, change <username> to your username*

```
  git remote add origin git@github.com:<username>/Ghost-Admin.git

​
```

*Quick check that everything is on latest*

```

git checkout master && git pull upstream master

```

*Then return to Ghost root directory*

```
cd ../../
```

## 7.  **Run setup & install all dependencies**

The setup task will install dependencies, initialise the database, set up git hooks & initialise submodules and run a first build of the admin. The very first build generally takes a while.

*Only ever run this once*

```
 yarn setup
```

## 8. Start Ghost 

*Run Ghost in development mode*

```
grunt dev
```

 *Ghost is now running at http://localhost:2368/*

​          ![Ghost is now running at locally on port 2368](https://res.cloudinary.com/nextwebb-devs/image/upload/v1579910273/Screenshot_from_2020-01-25_00-57-19.png)

## 9. **Setup an admin account**

   **Ghost is now running at locally on port 2368/ghost http://localhost:2368/ghost/ **

 You will see the welcome page to setup the Ghost admin account.

![Ghost is now running at locally on port 2368/ghost](https://res.cloudinary.com/nextwebb-devs/image/upload/v1579910322/Screenshot_from_2020-01-25_00-56-39.png)

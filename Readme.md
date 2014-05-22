# MikzAdminTool 3.0 - Setup

######Ver 1.0b


Prerequisites and steps to setup your development environment.


### Install Ruby
** Compass needs ruby to compile .sass **

- Windows - [http://rubyinstaller.org/downloads/](http://rubyinstaller.org/downloads/) Add C:\Ruby200-x64\bin to path.
- Mac OS X - Already Installed

After installation, Open a terminal / Commandline and enter:

`gem install compass`


---

### Install NodeJS

Download and install from:

- [http://nodejs.org/](http://nodejs.org/)

---

### Check out project from GIT

**Note gerrit is only avalible from sigma´s network**

1. Login in on http://gerrit:8080/ (Your AD account should work)
2. Create a ssh public key (or skip to step 3 if you have a key):
	1. From the Terminal or Git Bash, run ssh-keygen
	2. Confirm the default path .ssh/id_rsa
	3. Enter a passphrase or leave it blank.
    (Remember this passphrase, as you will need it to unlock the
    key whenever you use it!)
    4. Open ~/.ssh/id_rsa.pub and copy & paste the contents into
    the box on the gerrit web ui, then click on "Add".
    __Note that id_rsa.pub is your public key and can be shared,
    while id_rsa is your private key and should be kept secret.__
2. Go to "settings" in gerrit and add your ssh key.
3. Verify your key by open a ssh shell on port 29418:
    1. ssh fraand@gerrit -p29418
4. Clone the git repository in you development folder.
    1. git clone ssh://[username]@gerrit:29418/Danir/Mikz/Web/Publisher

5. Happy coding :)

6. Push all changes to gerrit:
`git push origin HEAD:refs/for/master`



--- 

### Initiate/start application

1. Open Terminal / Commandline, go to project basepath and enter:
2. `npm install -g grunt-cli` - installs [grunt-cli](https://github.com/gruntjs/grunt-cli) in gobal scope.
3. `npm install -g bower` - Installs [Bower](https://github.com/bower/bower) in global scope.
4. `npm install` - Installs project specific node modules described in *package.json*
    (Windows add path %appdata%\npm)
5. `bower install` - Installs project specific components to src/bower_components described in *bower.json* 
6. `grunt build` - Runs build-task specified in gruntFile.js, compiles .sass, concatenates .js, etc.
7. `grunt server` - Starts express-webserver and robohydra server in background to handle API calls

** After each update from GIT run commands 4-7 above. **


--- 

### Theme template ###

For references we included the original bootstrap theme selected for the project.
This theme is available by running the server-template task:

`grunt server-template` - to see available UI components.

--- 

### Add scripts to index.html ###
- `grunt scriptlinker` - If you have added .js files in 'src/app/' or 'src/common/' run grunt command to automatically add them to index.html

--- 

### Naming conventions ###

- Files and directories should be in lower case 
- Module names should be in lower case
- Directive names should be in lower case
- Controller names should be in camel case

** Note: This task is also included the build task. **


---



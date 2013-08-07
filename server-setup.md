# Setting up your dev-machine for the Modern Web

## Use-Case #1
A new web developer joins the team and need to get up and running.

## Use-Case #2
I need to start fresh, my machine is a mess, I have so many applications installed and I really need to 


# Preparing a MAC OSX machine

## 1. Install Xcode

Xcode is Apple's development environment for creating apps. Download it from:
[http://developer.apple.com/xcode](http://developer.apple.com/xcode)

	You must agree to the license by opening Xcode.app before proceeding.

The next set of applications will require the use of `Terminal`. 

## 2. Homebrew - Package Manager

Homebrew [http://brew.sh](http://brew.sh) is a package management system that simplifies the installation of software on the Mac OS X operating system.  

Homebrew will make the installation process easier. 

Open `Terminal` and enter the following command:

	ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)" 

-

	Press ENTER to continue.

-

	Enter System Password (your login password) 
-

	After installation is complete, be sure to run the 'brew doctor' command
	

## 3. Git - Source Control

Git is a distributed version control and source code management (SCM) system with an emphasis on speed. Now that you’ve got Homebrew installed, use it to install Git from within your `Terminal` by entering the following command line:

	brew install git

The Git installation is straightforward. 

## 4. Node.Js - Low-level Server Platform

Node.js is a software platform that is used to build scalable network applications. Node.js utilizes JavaScript as its scripting language, and achieves high throughput via non-blocking I/O and a single-threaded event loop.

Once again, Homebrew makes it easy to install the latest stable version for Node.js. Simply enter the following:

	brew install node

This should take about 4 minutes. Confirm the installation by checking Node latest version:

	node -v

And the great news is that Node Package Management (NPM) is also installed. Previous versions you had to install `npm` separately. Test it out:

	npm -v

Let me explain a bit about `npm` if you are not familiar.

### About npm

`npm` is a NodeJS package manager. As its name would imply, you can use it to install node programs. Also, if you use it in development, it makes it easier to specify and link dependencies.

I strongly encourage you not to do package management with sudo! Packages can run arbitrary scripts, which makes sudoing a package manager command as safe as a chainsaw haircut. Sure, it's fast and definitely going to cut through any obstacles, but you might actually want that obstacle to stay there.

I recommend doing this once instead:

	sudo chown -R $USER /usr/local

That sets your user account as the owner of the /usr/local directory, so that you can just issue normal commands in there. Then you won't ever have to use sudo when you install node or issue npm commands.


## 5. Bower - The Pkg Mgr for the Web

Bower [http://bower.io](http://bower.io)is a package manager for the web. It offers a generic, unopinionated solution to the problem of front-end package management, while exposing the package dependency model via an API that can be consumed by a more opinionated build stack. There are no system wide dependencies, no dependencies are shared between different apps, and the dependency tree is flat.

Bower is THE Package Manager to have if you want to manage installation dependencies for web development components, like AngulaJs, jQuery, etc.

Install Bower through `npm` as follows:

	sudo npm install -g bower

Check Bower's version by sending the following command:

	npm list -g

or 

	npm ls -g --depth=0

for the main branches only


We have more installation ahead, take a break and [check out all packages available through Bower](http://sindresorhus.com/bower-components/) 

## 6. Install SASS and Compass

By installing this CSS Preprocessor framewor now, will allow Yeoman - the scaffolding generator to include SASS in your new projects. Install it by using the following gem command:

	sudo gem install compass

## 7. Yeoman

Yeoman (or simply "Yo") is more than just a tool. It's a workflow; a collection of tools and best practices working in harmony to make developing for the web even better.
Our workflow is comprised of three tools for improving your productivity and satisfaction when building a web app: yo (the scaffolding tool), grunt (the build tool) and bower (the package management - already installed!).

- **Yo** scaffolds out a new application, writing your Grunt configuration and pulling in relevant Grunt tasks that you might need for your build.
- **Grunt** - is used to build, preview and test your project, thanks to help from tasks curated by the Yeoman team and grunt-contrib.
- **Bower** - once more, is used for dependency management, so that you no longer have to manually download and manage your scripts.

Then install the required tools globally by running:

	npm install -g yo

This will install **Grunt** automatically.

## 8. Grunt

If you've been following this guide, Grunt is already installed via Yeoman. Let's describe Grunt a bit further:

Grunt is a JavaScript Task Runner. 

### Why use a task runner? 
In one word: automation. The less work you have to do when performing repetitive tasks like minification, compilation, unit testing, linting, etc, the easier your job becomes. After you've configured it, a task runner can do most of that mundane work for you—and your team—with basically zero effort.

### Why use Grunt?
The Grunt ecosystem is huge and it's growing every day. With literally hundreds of plugins to choose from, you can use Grunt to automate just about anything with a minimum of effort. If someone hasn't already built what you need, authoring and publishing your own Grunt plugin to npm is a breeze.

More on how to use Grunt later.

## 9. SSH access






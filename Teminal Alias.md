# How to create shortcut aliases
Aliases can improve your workflow and save you some time while using Terminal's command line. There are two types of aliases:

- Temporary - gets lost once you log out; 
- Permanent - gets recorded in your user profile and is available whenever you need.
 

## Setting up a new Temporary Alias
Open Terminal (by going to Applications -> Utilities -> Terminal)

Lets say you want to create a simple shortcut alias called `go_proj` to change from your current directory to your favorite projects folder called `Projects`:

	alias go_proj="cd ~/Projects"
    
The following instruction will create a new alias called `go_server` to connect to  server called `DevServer` via ssh.

	alias go_server="ssh DevServer@192.168.1.100"


### Important Note About Temporary Aliases 
As soon as you log out, the aliases we defined this way are gone. They aren’t saved anywhere, and the OS wasn’t told to set them up again once we log back in. So how do we handle this issue? The **`.profile`** file.

***

## What is .profile?
If a file’s name starts with the “.” (dot) character, that file is hidden
The “.” (dot) in front of certain file names means the file is “hidden.”

## Finding .profile
But if it’s hidden, how do we see it? How can we edit a file we’re not supposed to see? Start `Terminal`, and go to your home folder by typing the following:

	cd ~/

Tip: You can also go to your home folder by just typing cd and following it up by a space character.

Once there, type this:

	ls -a

This lists (ls) the contents of the folder you are in, and the -a parameter we added tells it to show “all” files – including hidden ones.

Use any of the two methods above to find out which hidden files your home folder contains, and make sure a .profile or .bash_profile file is there. If either of them exist, great. 

**If they aren’t present, create the .profile file** by using the Terminal, as follows:

	touch ~/.profile

One way or the other, we are now certain the .profile file exists. Now let’s add some commands to it!

to edit the .profile file simply enter the following to open the file on **TextEdit**:

	open -e ~/.profile


*** 

## Setting up a new Permanent Alias

Once the .profile is opened in your text editor, all you'd have to do is to add the command line, one per line. A good practice is to add a comment line before each command explaining what the command will do. 

	# Go to my Projects folder
	alias go_proj="cd ~/Projects"
	
    # SSH into my development server terminal
	alias go_server="ssh DevServer@192.168.1.100"

Now save and quit. 

### Important Note
Every time you change the .profile file mid-session like we just did, it needs to be re-loaded to take effect.

You would usually do this manually by typing

	source ~/.profile

or just

	. ~/.profile

## Conclusion
Once done, give it a go. Type your new alias and see if it works. Once you reboot or log-out and log-in again, the alias should still be alive and should still work.

-mp

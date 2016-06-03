# What is the Learn IDE?

The Learn IDE is a cross-platform application (OS X, Windows) that allows Learn students to write code in a modern text editor (Atom) and use a fully-configured Terminal. The application is our own custom fork of GitHub's Atom text editor, that adds to it a virtualized Terminal. The Learn IDE runs locally rather than in the browser, and on top of our own infrastructure.

The Learn IDE app runs against a Learn IDE server in our cloud, to which all users connect. The file system that is exposed to you in the Learn IDE (in your code directory, seen in the file browser) is synchronized to the Learn IDE server. All commands that you, the student, type into the terminal window are relayed to the Learn IDE server, and the response is echoed from that server. Because the Learn IDE server has been configured to have all packages required to develop on Learn, there is less probability of a development environment configuration issue, which can be a time consuming troubleshooting process. 

# What operating systems and versions does the IDE work on?

OSX 10.8+

Windows 7+ (8+ preferred)

# Do I have to use the IDE?

Yes. If you are unable to use the IDE due to your operating system not meeting the requirements, please email support+ide@learn.co

# How do I check which version of the IDE I am using?

Mac: open the Atom dropdown menu.

Windows: open the Help dropdown menu.

# Where can I find my Oauth token? 

http://learn.co/ile/token

# How can I change the font size in the IDE terminal? In the text editor?

`CMD + +/-` on Mac, `ALT + up/down` on Windows.

# How can I download the IDE?

The link to get set up with the Learn IDE is: https://learn.co/ide.

# How can I fully delete the IDE?

We recommend using an app cleaner to ensure it is fully deleted. This is an app cleaner we can recommend for Mac users: https://freemacsoft.net/appcleaner/.

# The IDE isn't working for me. The text is greyed out in the terminal and I can’t type. What do I do?

Is there a red DISCONNECTED warning at the bottom right of the terminal? 

![disconnected] (https://s3.amazonaws.com/ironboard-learn/help-center/disconnected.png)

To reconnect go to Packages-->Learn.co-->Reconnect.

![reconnect] (https://s3.amazonaws.com/ironboard-learn/help-center/reconnect.png)

If you are connected you will see the following:

![connected] (https://s3.amazonaws.com/ironboard-learn/help-center/connected.png)

# I see 'Not authorized.' in the terminal. What does this mean, and how can I fix it?

This means you have entered your OAuth Token incorrectly. To fix this, you should click on Atom-->Open Your Config (Mac) or File-->Open Your Config (Windows). 

![open-config] (https://s3.amazonaws.com/ironboard-learn/help-center/open-config.png)


Atom will open a file with lines that look something like this:

```
"integrated-learn-environment":

    oauthToken: "oauth_token_here"
```
! [oauth-token] (https://s3.amazonaws.com/ironboard-learn/help-center/oath-token.png)

Now visit https://learn.co/ile/token, correctly paste it into this file between the “ “, and then save. Then fully quit the Learn IDE (using the Atom or File menu). Just clicking the (X) at the corner of the window to close is not enough. You MUST use the file menu to fully quit.

If your config file does not already have the code snippet, just add those lines right under the `userId:...` line as seen in the above screenshot.

# I see 'No passwd entry for user "username"' and cannot work in the IDE, how can I fix this?

This means one of two things:

1. Your account was not created on the IDE server

or

2. You changed your GitHub username between when your account was created on the IDE server and when you tried to connect.
First double check that the token is there. (See instructions above for 'Not authorized.' error message to check for the token).

Then ask for help from the Learn Experts in Ask a Question, explaining the steps you have taken to investigate the issue.

# Can I use Learn IDE across more than one computer? 

Yes, the Learn IDE can be used across multiple computers, but it is important that you understand how it works. When you open a new lab in the Learn IDE, you are downloading (or to use the git word, cloning) your GitHub fork of the lab from your computer to the Learn server (this is what you are seeing in the terminal). This then triggers the lab to be downloaded to your local computer as well (this is what you are seeing in the text editor portion). As you make changes to the files in the lab and save the files, the changes are updated on the copy stored on the Learn server. The true record of all your labs should be stored on GitHub (this happens automatically when you do learn submit). Even though your labs are on the Learn server, please do not consider them saved or accessible from there. 

When you install the Learn IDE on another computer, all your files on the Learn server are NOT auto-downloaded to your local computer. You need to re-download each lab you want to work on from Github. If this lab is already stored on the Learn server (you’ll be able to see it by typing ls in the /labs directory in your Learn IDE terminal) you’re going to have to remove it before re-downloading it. Make sure that your work is pushed to GitHub on whatever computer you started the lab on before removing it from the Learn IDE!

Instructions to get an already started or already completed lab from one computer to another with the Learn IDE:

1. From the computer that has your latest work, make sure your code has been pushed up to GitHub by using `learn save`
2. In the Learn IDE, you'll want to remove the stale copy of this repository with `rm -rf REPOSITORY_NAME` from within your labs directory (where REPOSITORY_NAME is the name of the lab on GitHub). WARNING: if you haven’t pushed your work to GitHub with learn save you will lose your un-saved changes.
3. Run `learn open REPOSITORY_NAME`

The Learn IDE will now have an updated copy of your work, and will automatically remain synced to this computer. If you want to switch back to a different computer, you'll need to follow the above steps again.

# I cloned a lab but can't see it in the file tree. What’s going on?

Are you using the IDE across multiple computers? If so, the latest code may not show up in the Learn IDE. In this case, follow the instructions in the scenario above (Can I use Learn IDE across more than one computer?).

If you are not using multiple computers, confirm that nothing is syncing by following these steps in the IDE:

1. `cd ~/code` 
2. `touch testfile.txt`

If `testfile.txt` shows up in your local file tree, try deleting the lab that isn't showing up by using `rm -rf ~/code/labs/name_of_lab` and then trying to re-open the lab. If `testfile.txt` does not show up in your local file tree:  

3. Quit and restart the Learn IDE. JUST PRESSING THE (X) AT THE TOP OF THE WINDOW AND CLOSING IT IS NOT ENOUGH, you must close the Learn IDE by using the menu options.
4. `cd ~/code` 
5. `touch testfile2.txt`

If `testfile2.txt` shows up in your local file tree now, delete the lab that isn't showing up (using the `rm -rf` command notes above) and re-clone. If `testfile.txt` still doesn't show up, please use Ask a Question for assistance, and explain the steps you have taken to investigate the issue.

# File/image is blank
If you are on an html lab and can't see the result of your work (images), do the following: 

1. Make sure you are using the most up to date version of the IDE.
2. Type `httpserver` and you will see a link to go to for an http server. 

# How do I view/open an HTML file OR I can't open index.html file from command line

Make sure you are using the most up to date version of the IDE. 

If you are then do the following:

Run `httpserver` from the command line and then navigate to the address it gives you which should look something like this: `Serving HTTP on 159.203.117.55:3107`, navigate to `159.203.117.55:3107` in the browser and it should show you the file.

# I installed the IDE and now Atom doesn't work, how do I go back?

Make sure you are using the most up to date version of the IDE.
When the IDE was installed, it created a backup file for your original Atom settings. If you installed the IDE a second time though, it will have overwritten that backup file during the second install.

To revert back to your original setup, first make sure that the Learn IDE and Atom are both closed. 

Then:
1. Back up your back up with (do this in your native terminal, not the IDE): `cp -R ~/.atom.bak ~/.atom.bak2`
2. Overwrite the .atom file with your backup (do this in your native terminal, not the IDE): `mv ~/.atom.bak ~/.atom`

# When I click on the Learn Open button, it opens Atom, but not the IDE

Close Atom using the file menu (not just the X in the top corner). Then open the IDE directly. Then while the IDE is open, click on the learn open button and it should open in the IDE instead of raw Atom.

# The "Learn Open" button on learn.co isn't working

See the information above (When I click on the Learn Open button, it opens Atom, but not the IDE), but another option for fixing this is to type "learn open" in the command line of the IDE. That should open your next lab.

# The 'learn open' command in the IDE is opening the wrong lab

If that is the case, go to learn.co, click on the Octocat icon to open the repository for the lab. Cut and paste the repo name (e.g. for the gets CLI input lab on fullstack, click on the Octocat just to the right of the open button to see the repo and then the command you'd run would be `learn open ruby-gets-input-v-000`.) That should open the proper lab, and when you run the tests or submit your changes that should update your "current lab" setting in Learn.

# My lights aren’t responding to the work I’m doing in the IDE, how can I fix this?

Check that you’re using an up to date version of Google Chrome. If that doesn’t fix the issue, use Ask a Question to receive assistance.

# My IDE does not show the file tree, how can I get it to appear? 

Check to make sure you are using the most up to date version of the IDE. If you are, Click `View -> Toggle Tree View`.

# I can’t see the file tree and atom `<file-name>` opens blank files, how can I fix this?

Remove the local copy of the Learn IDE application, and install a new version of the application from learn.co/ide.

# How can I upload files to my repo using the IDE?

Right click on the folder where you would like to add the file to the Learn IDE and select Import File. Importing your files this will will correctly trigger the proper Learn IDE sync process. Note, max file size is ~15MB

# How can I run multiple processes in my IDE terminal?

For some labs, you may need to run multiple processes (think `jekyll serve` in one and `learn` in the other - example: https://github.com/learn-co-curriculum/oo-student-scraper). This can easily be accomplished by running tasks in the background. Add an & to the end of your command (example: `jekyll serve &`) and it will now run in the background. Its output will still pop up in your terminal, but you'll get use of the prompt back.

You can always check what jobs are running by using the jobs command in terminal. This will display a list of currently running processes along with a number (starting at 1) associated with each job. Use `fg` and then the job number (example: `fg 1`) to bring any of the background jobs to the foreground. You'll need to do this to kill your background servers when you're done with them.

# File system blob store error
You may log in and see an error that looks like the photo below. Your Learn IDE does not load up properly.

! [file-system-blob-store-error] (https://s3.amazonaws.com/ironboard-learn/help-center/file-system-blob-store-error.png)

To fix this, go to the `~/.atom` directory using your computer’s local terminal, NOT the terminal in the Learn IDE and re-name the file blob-store to blob-store-backup.

# I'm getting an "Uncaught Error - Repository Has Been Destroyed" error message. What do I do?

If you get an error that looks like the one below:

! [uncaught-error-repo-destroyed] (https://s3.amazonaws.com/ironboard-learn/help-center/uncaught-error-repo-destroyed.png)

First try removing the troublesome repo with rm -rf ~/code/name_of_the_repo (if it's apparent which repo it is) and then re-cloning it (you can do this with learn open or the Open button in Learn.

If that doesn't work, uninstall and re-install the Learn IDE from learn.co/ide.

# I keep getting a “Reconnecting...” message, how can I fix this?

Most likely your ports are blocked on your network. Let’s try checking for this using the following steps:

Mac

In the your local Terminal (not the IDE), run: telnet ile.learn.co 4464 and telnet ile.learn.co 4463. After you run each command, you'll have to use ctrl + c to kill the connection. Each command should return something that looks like this:

```
Trying 159.203.117.55...
Connected to ile.learn.co.
```
Escape character is '^]'.

Windows

There is a bit of set up for Windows users. The steps are as follows:

1. Open Control Panel and click Programs > Turn Windows Features On or Off
2. Wait for dialog box to finish loading (can take a little while sometimes)
3. Check 'Telnet Client' if it isn't already, then click 'Ok'
4. Open a Command Prompt
5. Type: telnet then press Enter
6. Type: o ile.learn.co 4464 then press Enter <-- This should just hang
7. Type: ctrl + ]
8. Type: o ile.learn.co 4463 then press Enter <-- This should also just hang
9. Type: ctrl + ]

If either step 6 or step 8 returns something like: `Could not open connection to the host on port xxxx`, then there is an issue with the your network settings and we recommend trying to use a different network (try using a different netweork and see if it works. You can also try downloading a VPN and connecting through that).

# When I clone/open the lab, the IDE disconnects and/or I am missing lab content. What do I do?

Labs with large amounts of assets/files can cause issues. If a lab has a ton of content in it, the IDE might crash when it tries to sync the cloned lab content to the local storage. It will abruptly disconnect and some of the content won’t be copied over.

Reconnect through Packages > Learn.co > Reconnect.

If you’re missing content after reconnecting (this will probably happen): Then run `ls` and compare the files in command line to the files in the sidebar/tree. For each missing file, you can run `git checkout origin/master -- [path to file ]`. 

So, for example, if I'm missing the `index.html`, I run `git checkout origin/master -- index.html` (you can also put the name of a folder and it will copy down that folder and it's respective files).

We have seen this happen with the following labs thus far: 

1. learn-deploy-on-day-one 
2. html-album-cover

# The IDE installs and opens without Packages > Learn.co in the menu, or any command line authentication prompt etc.

If you're on a Windows machine, make sure the .atom folder is in `C:\Users\[your username]` if not, move it there and relaunch.

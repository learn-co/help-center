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


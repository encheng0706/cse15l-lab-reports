# Logging onto *ieng6*:<br>
## Installing VS Code:
First, you need to use Visual Studio Code (VS Code), where you can download from 
[here](https://code.visualstudio.com/download), as shown in the screenshot below.

![](VSCodeDownloadPage.png)

## Remotely Connecting:<br>
Before you can remotely connect to your course-specific account, you will need to also download openSSH. [Here](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse) is a Microsoft page to guide the process. <br>
Once you are finished with this setup, you can start the remote connection process. Open the terminal on VS Code using `` Ctrl + ` ``. Inside of the terminal, type the command:
<br><br>
`ssh cs15lsp22XX@ieng6.ucsd.edu`
<br><br>
The email will be different based on the course, and the XX will be specific letters for your specific account. Do an account lookup on [https://sdacs.ucsd.edu/~icc/index.php](https://sdacs.ucsd.edu/~icc/index.php/).<br>
Once you type in your password, you will be successfully connected!<br>
![Remote Connect Example](RemoteConnectTerminal.png)


## Trying Different Commands:<br>
There are many commands that will be used in the terminal. Here are some examples of useful commands and what they do: <br><br>
`ls` ------------ lists out the files and folders in the current directory<br>
`ls -a` -------- lists out everything, including hidden files<br>
`cd` ------------ change directory, follow it up with the file you want to go to<br>
`cd ..` -------- go back a directory<br>
`cp` ------------ copies a file or directory<br>
`scp` ----------- secure copy<br>
`cat` ----------- shows what is inside of the file, the contents of the file<br>
<br>
![](SScommandsExample.png)


## Moving files with `scp`:<br>
After working on something on your local computer, you can move your files between computers. In order to move files from a local computer to a remote computer, the command `scp` is used. **Make sure to use it in the client terminal, so not while logged into the remote computer.**

![](Screenshot(19).png)<br>

After this, you can use the `ls` command again inside of the remotely logged in terminal to check and see that the file was successfully moved over.<br>

![](Screenshot(20).png)<br>


## Setting an SSH Key:<br>
In order to speed up the process of working remotely, we can set up an SSH Key. What is does it basically save your login information so that you can login in quickly without needing to enter a password. Use the command:
<br>
`ssh-keygen` <br>
When it asks for a passphrase, just press `Enter` twice in order to use an empty passphrase. <br>
If you are on Windows, do the command:<br>
`ssh-keygen -t ed25519`<br>
Continue with:<br>
`ssh cs15lsp22XX@ieng6.ucsd.edu`<br>
On the remotely logged in terminal (server):<br>
`mkdir .ssh` and then log out<br>
Go back to the local (client) terminal:<br>
`scp /Users/<user-name>/.ssh/id_rsa.pub cs15lsp22XX@ieng6.ucsd.edu:~/.ssh/authorized_keys`<br>
The path will differ based on where you stored the key creation file.<br>
After this, you should be able to log on without a password!
<br>
![](Screenshot(21).png)


## Optimizing Remote Running:<br>
You can further optimize remote running by speeding up the process of dealing with the commands in the terminal. Some useful tips are that:<br>

- you can use the `Up Arrow` key to redo previous commands that were typed in
- use an `;` to seperate different commands while writing them in the same line
- putting a command in `" "` after using `ssh` to login will streamline the process of logging in, running the command, and then logging out into 1 line.<br>

For example, I was able to move and run a file with two lines, and four keystrokes:
![](Screenshot(22).png)
![](Screenshot(24).png)
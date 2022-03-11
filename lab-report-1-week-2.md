[Lab Report 1](https://richard21a.github.io/cse15l-lab-reports//lab-report-1-week-2.html)
[Lab Report 2](https://richard21a.github.io/cse15l-lab-reports/lab-report-2-week-4.html)
[Lab Report 3](https://richard21a.github.io/cse15l-lab-reports/lab-report-3/lab-report-3-week-6.html)
[Lab Report 4](https://richard21a.github.io/cse15l-lab-reports/lab-report-4/lab-report-4-week-8.html)
[Lab Report 5](https://richard21a.github.io/cse15l-lab-reports/lab-report-5/lab-report-5-week-10.html)
# Step 1: Installing VScode

Visual studio code is an editor commonly used to write code. You can download it for free on the internet. Here is where you can download it:
[VScode Download link](https://code.visualstudio.com/download)

After downloading it, open VS code and you should see this screen:

![Image](vscode.png)

# Step 2: Remotely Connecting

We're going to connect to the computers in UCSD using ssh. In order to do this, we need to first reset our password for ssh account for CSE15l. I found this works most reliably in windows explorer. After resetting the password, log in to ssh using the command shown below:

```ssh cs15wi22aav@ieng6.ucsd.edu```

![Image](remote.png)

# Step 3: Trying some Commands

Now we are going to try out some essential commands that we can use in the terminal. Examples of these commands being run is shown below:

`cd` : Change directory

`ls` : Lists the things in the current directory

`mkdir` : Make a new directory

![Image](commands.png)

# Step 4: Moving files with SCP

Now we are going to learn how to move files from client(your computer) to server(ssh). To do this, run the following command: `scp WhereAmI.java cs15lwi22aav@ieng6.ucsd.edu:~/` in your own computer terminal(WhereAmI.java is the file in the client that we want to move to the server).

![Image](scp.png)

# Step 5: Setting up ssh keys

Notice that we have to put in our password whenever we log into ssh or put a file in. There is a way to bypass this and that is by setting up ssh keys. One important note for Windows users is to first open a powershell window as administrator. The process of achieving this is shown below:

`ssh-keygen -t ed25519`, `Get-Service ssh-agent`, `Start-Service ssh-agent`, and `ssh-add` commands are used to generate a key in the client.

![Image](keygen.png)

We then connect the key to the server with the following command: `scp ~/.ssh/id_ed25519.pub cs15lwi22aav@ieng6.ucsd.edu:~/.ssh/authorized_keys`

As shown in the bottom of the image below, we are now able to connect to ssh without entering our password.
![Image](keygen2.png)

# Part 6: Optimize remote setting:

In addition to ssh keys, there are several ways to optimize a remote enviroment. One way is to write whatever commands that you want to run in quotes at the end of the ssh command. This will make it so that after you enter ssh the terminal will execute the command in quotes and exit the server without using the `exit` command. In addition to this, we can use semi colons to run multiple commands at the same time using one line. Lastly, we can use the TAB key to autocomplete file names. An example of these optimizations being used: `scp WhereAmI.java cs15lwi22aav@ieng6.ucsd.edu "javac WhereAmI.java ; java WhereAmI"` (Approxmate keystrokes:50). To achieve the same result without these optimizations, we would have to write: `scp WhereAmI.java cs15lwi22aav@ieng6.ucsd.edu` , `javac WhereAmI.java` , `java WhereAmI`, and `exit` (Approximate keystrokes:85) 

![Image](optimal.png)
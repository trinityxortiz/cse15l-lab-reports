**Lab Report #1: Logging Into UCSD Servers**
=============
Some coding projects require the use of a UNIX or LINUX system. For the Windows OS system, we must login to the UCSD remote server to run our programs since the server uses a LINUX based system. 

To start running your programs with ease on a linux operating system using your own personal console, you must do the following:

## **Install Visual Studio Code**
<<<<<<< HEAD

- To download VS Code go to the [VS Code Dowload Page](https://code.visualstudio.com/)  

- Click on the "Download for Windows" button to download and install VS Code onto your local computer

=======
    - To download VS Code go to the [VS Code Dowload Page](https://code.visualstudio.com/)  
        - Click on the "Download for Windows" button to download and install VS Code onto your local computer
>>>>>>> 6d26a23cc542b602b31a6f038d5ce1aa9d960e85
    ![VS Code Dowload Page](Images/VSCode-DownloadScreen.png)

    - Once you have installed VS Code, you should see a screen similar to this &darr; (NOTE: Your screen will look different!)
    ![VS Code Dowload Page](Images/VSCode-Home.png)
<<<<<<< HEAD

## **Connect to the UCSD Server**

=======
## **Connect to the UCSD Server**  
>>>>>>> 6d26a23cc542b602b31a6f038d5ce1aa9d960e85
In the UCSD CSE courses, you may be given a specific course account which are similar to accounts that you may given in your future career. For Windows users, we need to take one extra step before we attempt to connect to the servers.   
- [Install OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)
- Find your course-specific account [here](https://sdacs.ucsd.edu/~icc/index.php) and take note of what your password is.
    - If you don't know your password, reset it using your UCSD credentials. It may take a few minutes to an hour for the system to update your password.
    - You should see an account with the class name and 3 letters following it
        - For example 'cs12sp22xxx' where xxx is 3 letters specific to your account.

![ETS Lookup Page](Images\ETS-Lookup.png)

- Now open a terminal either in VSCode or your computer's command prompt. 
![How to open the terminal](Images\TerminalView.png)

The terminal should now be open and it should look something like this:
```
PS C:\Users\usr 
```
Now we can connect to ther server. At UCSD we will be connecting to the ***ieng6.ucsd.edu*** server.  
- Type the following into your terminal using this format: username@ieng6.ucsd.edu where xxx is your specific account letters.
    ```
    PS C:\Users\usr ssh cs15lsp22xxx@ieng6.ucsd.edu
    ```
    During your first time logging in, you may be prompted with a message asking if you want to continue connecting to the server. 
    ```
     PS C:\Users\usr ssh cs15lsp22xxx@ieng6.ucsd.edu

     The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.

     RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.

     Are you sure you want to continue connecting (yes/no/[fingerprint])?
    ```
    Type yes and press enter. You will be prompted for your password.
    ```
    Password:
    ```
    Type your password and you should see something like this:
    ![ssh view after password](Images\ssh-login.png)
<<<<<<< HEAD

    _Congrats, you have now successfully logged into the UCSD server remotely!_
## **Running Commands on Your Computer and the Remote Computer**
-  Now that you can login in remotely, let's try running some commands on both your local comupter and the server.
=======
    Congrats, you have now successfully logged into the UCSD server remotely!
## **Running Commands on Your Computer and the Remote Computer**
    > Now that you can login in remotely, let's try running some commands on both your local comupter and the server.
    
>>>>>>> 6d26a23cc542b602b31a6f038d5ce1aa9d960e85
    
    ```
    cd ~
    ```
    &rarr; Takes you to the home directory 
    ```
    cd <directory>
    ```
    &rarr; Changes the directory to the specified directory
    ```
    pwd
    ```
    &rarr; Prints the working directory
    ```
    mkdir
    ```
    &rarr; Makes a new directory
    ```
    cp <file or directory> <destination directory>
    ```
    &rarr; Copies a file or directory to the directory specified
    ```
    ls -lat
    ```
    &rarr; Shows a list of all files and directories within the current directory by date
    ```
    ls -a
    ```
    &rarr; Shows all files and directories within the current directory
    ```
    ls
    ```
    &rarr; Lists files and directories within the current directory
   
**To try any of these commands...**   
    1. Open your terminal  
    2. Type in the command and any files or directories you want to see or go to
    
<<<<<<< HEAD
This is an example of the cd command on the remote server:
![command practice](Images\cd-command-remote.png)

## **Moving Files using scp command**
Copying files back and forth between computers is important. We will now learn how to copy a file from a computer to a remote computer.   
We will do this by creating a java file on our local computer named WhereAmI.java with these contents:

```
class WhereAmI {
    public static void main(String[] args) {
        System.out.println(System.getProperty("os.name"));
        System.out.println(System.getProperty("user.name"));
        System.out.println(System.getProperty("user.home"));
        System.out.println(System.getProperty("user.dir"));
    }
}
``` 
- Now on your local terminal, run the file using java and javac
- Now type the following using your username:
```
scp WhereAmI.java cs15lsp22xxx@ieng6.ucsd.edu:~/
```
You will be prompted for a password then you should see something like this:
![scp command](Images\scp-execution.png)

- Now login to the server using the ssh command. Mine does not show the password prompt but your screen should.
- Type this command:
```
$ ls 
```
- You should now see a list of files in your home directory on the remote server. This will now include WhereAmI.java.
![ls in remote terminal](Images\scp.png)
- If you run the javac and java commands on the files, you will see results related to the remote computer on the server instead of your local computer.
## **Setting an SSH Key**
> Entering your password is tedious and time consuming. We will now be setting up an SSH key which wil automatically enter in your password for you and you will no longer need to input your password when using ssh or scp.  
The *ssh keys* let you do this. Using the ssh-keygen command creates a pair of files called public key and private key.  
The private key is stored on your computer and the public key is copied to the server.  
These keys will be used with the ssh command instead of your password. 

- Open the terminal on your computer.
- Type:
```
ssh-keygen -t ed25519
```
You will be prompted to enter a file like this:
```
Generating public/private rsa key pair.

Enter file in which to save the key (/Users/<user-name>/.ssh/id_ed25519): 
```
- Type the path by copying what is in the parenthesis.
    - /Users/usr/.ssh/id_ed25519
- You will be prompted with the following but just press enter 
```
Enter passphrase (empty for no passphrase): 
```
Your screen should look something like this:
![keygen process](Images\keygen.png)

- Now we must copy the public key to the .ssh directory on the server
    - login to the remote server
    - make a directory called .ssh with a folder called authorized_keys
    ```
    $ mkdir .ssh
    $ cd .ssh
    $ mkdir authorized_keys
    ```
    - Logout by typing exit and this will take you back to your local terminal.
    ```
    $ exit
    ```
    - Now type the following into your local terminal using your class account:
    ```
    $ scp /Users/usr/.ssh/id_ed25519.pub cs15lsp22xxx@ieng6.ucsd.edu:~/.ssh/authorized_keys
    ```
    - Now login using ssh and you should be logged in without a password!
    ![ssh without a password](Images\ssh-no-pw.png)

## **Optimizing Remote Running**
 Not having to enter a password each time is great, but we can make it even better!
- Use semicolons to run multiple commands using one line.
    - For example, this logs into the server and lists the home directory contents on the remote server:
    ```
    $ ssh cs15lsp22xxx@ieng6.ucsd.edu "ls -l"
    ```
    ![ssh and ls-l combined command](Images\ssh-combined-lslat.png)
    - You can also do this with running and compiling files:
    ```
    $ ssh cs15lsp22xxx@ieng6.ucsd.edu; javac [file to compile]; java [file name without .java]
    ```
    - To combine commands, separate them with a semicolon "[command]; "
    
=======
    This is an example of the cd command on the remote server:
    ![command practice](Images\cd-command-remote.png)

## **Moving Files using scp command**
Copying files back and forth between computers is important. We will now learn how to copy a file from a computer to a remote computer. 
    - We will do this by creating a java file on our local computer named WhereAmI.java with these contents:
    ```
    class WhereAmI {
        public static void main(String[] args) {
            System.out.println(System.getProperty("os.name"));
            System.out.println(System.getProperty("user.name"));
            System.out.println(System.getProperty("user.home"));
            System.out.println(System.getProperty("user.dir"));
        }
    }
    ``` 
    - Now on your local terminal, run the file using java and javac
    - Now type the following using your username:
    ```
    scp WhereAmI.java cs15lsp22xxx@ieng6.ucsd.edu:~/
    ```
    You will be prompted for a password then you should see something like this:
    ![scp command](Images\scp-execution.png)

    - Now login to the server using the ssh command. Mine does not show the password prompt but your screen should.
    - Type this command:
    ```
    $ ls 
    ```
    - You should now see a list of files in your home directory on the remote server. This will now include WhereAmI.java.
    ![ls in remote terminal](Images\scp.png)
    - If you run the javac and java commands on the files, you will see results related to the remote computer on the server instead of your local computer.
## **Setting an SSH Key**
   > Entering your password is tedious and time consuming. We will now be setting up an SSH key which wil automatically enter in your password for you and you will no longer need to input your password when using ssh or scp.  
   The *ssh keys* let you do this. Using the ssh-keygen command creates a pair of files called public key and private key.  
   The private key is stored on your computer and the public key is copied to the server.  
   These keys will be used with the ssh command instead of your password. 

   - Open the terminal on your computer.
   - Type:
   ```
   ssh-keygen -t ed25519
   ```
   You will be prompted to enter a file like this:
   ```
    Generating public/private rsa key pair.

    Enter file in which to save the key (/Users/<user-name>/.ssh/id_ed25519): 
    ```
    - Type the path by copying what is in the parenthesis.
       - /Users/usr/.ssh/id_ed25519
    - You will be prompted with the following but just press enter 
    ```
    Enter passphrase (empty for no passphrase): 
    ```
    > Your screen should look something like this:
    ![keygen process](Images\keygen.png)

    - Now we must copy the public key to the .ssh directory on the server
        - login to the remote server
        - make a directory called .ssh with a folder called authorized_keys
        ```
        $ mkdir .ssh
        $ cd .ssh
        $ mkdir authorized_keys
        ```
        - Logout by typing exit and this will take you back to your local terminal.
        ```
        $ exit
        ```
        - Now type the following into your local terminal using your class account:
        ```
        $ scp /Users/usr/.ssh/id_ed25519.pub cs15lsp22xxx@ieng6.ucsd.edu:~/.ssh/authorized_keys
        ```
        - Now login using ssh and you should be logged in without a password!
        ![ssh without a password](Images\ssh-no-pw.png)

## **Optimizing Remote Running**
    - Not having to enter a password each time is great, but we can make it even better.
    - Use semicolons to run multiple commands using one line.
        - For example, this logs into the server and lists the home directory contents on the remote server:
        ```
        $ ssh cs15lsp22xxx@ieng6.ucsd.edu "ls -l"
        ```
        ![ssh and ls-l combined command](Images\ssh-combined-lslat.png)
        - You can also do this with running and compiling files:
        ```
        $ ssh cs15lsp22xxx@ieng6.ucsd.edu; javac [file to compile]; java [file name without .java]
        ```
        - To combine commands, separate them with a semicolon "[command]; "
        
>>>>>>> 6d26a23cc542b602b31a6f038d5ce1aa9d960e85











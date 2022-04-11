**Lab Report #1: Logging Into UCSD Servers**
=============
Some coding projects require the use of a UNIX or LINUX system. For the Windows OS system, we must login to the UCSD remote server to run our programs since the server uses a LINUX based system. 

To start running your programs with ease on a linux operating system using your own personal console, you must do the following:

1. **Install Visual Studio Code**
    - To download VS Code go to the [VS Code Dowload Page](https://code.visualstudio.com/)  
        - Click on the "Download for Windows" button to download and install VS Code onto your local computer
    ![VS Code Dowload Page](Images/VSCode-DownloadScreen.png)
    - Once you have installed VS Code, you should see a screen similar to this &darr; (NOTE: Your screen will look different!)
    ![VS Code Dowload Page](Images/VSCode-Home.png)
2. **Connect to the UCSD Server**  
In the UCSD CSE courses, you may be given a specific course account which are similar to accounts that you may given in your future career. For Windows users, we need to take one extra step before we attempt to connect to the servers.   
    - [Install OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)
    - Find your course-specific account [here](https://sdacs.ucsd.edu/~icc/index.php) and take note of what your password is.
        - If you don't know your password, reset it using your UCSD credentials. It may take a few minutes to an hour for the system to update your password.
        - You should see an account with the class name and 3 letters following it
            - For example 'cs12sp22***' where *** is 3 letters
    ![ETS Lookup Page](Images\ETS-Lookup.png)
    - Now open a terminal either in VSCode or your computer's command prompt. 
    ![How to open the terminal](Images\TerminalView.png)
    
    The terminal should now be open and it should look something like this:

    ```
    PS C:\Users\usr 
    ```
    Now we can connect to ther server.  
     At UCSD we will be connecting to the ***ieng6.ucsd.edu*** server.  
    Type the following into your terminal using this format: username@ieng6.ucsd.edu where xxx is your specific account letters.
    ```
    PS C:\Users\usr ssh cs15lsp22xxx@ieng6.ucsd.edu
    ```
    During your first time logging in, you make be prompted with a message asking if you want to continue connecting to the server. 
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
    Congrats, you have now successfully logged into the UCSD server remotely!
3. Running Commands on Your Computer and the Remote Computer
    > Now that you can login in remotely, let's try running some commands on both your local comupter and the server.
    
    
    ```
    cd ~
    ```
    ```
    cd 
    ```
    ```
    pwd
    ```
    ```
    mkdir
    ```
    ```
    cp
    ```
    ```
    ls -lat
    ```
    ```
    ls -a
    ```
    ```
    ls <directory>
    ```
    ```
    cd ~
    ```

    


- Trying Commands
- Moving Files using scp command
- Setting an SSH Key
- Optimizing Remote Running









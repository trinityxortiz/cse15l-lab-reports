# Lab Report 3
## Streamlining ssh Configuration  
1. First you need to go to your home directory then find and open the .ssh folder.  
![.ssh directory contents](Images\Lab5\ssh_dir_view.png)

2. Once the .ssh folder is opened, open the file named 'config' in any text editor.
    - If there is no config file, you can just create a file with the name 'config' within the directory or open the terminal and use this command while in the .ssh directory:

    ```
    touch config
    ```  
3. Start by writing '# [Description]' so you remember what it is for.  
4. Next type 'Host' followed by a nickname for the login  
5. Then indent and type 'HostName' followed by the server name which is the part of your login after the '@'.  
6. Press enter and type 'User' followed by your login name which is the part before the '@'.  
7. If you happen to have multiple keys then you can also add 'IdentityFile' followed by the path to the private key file  
You should now be able to login using the nickname you created!  
![view of config file in vscode](Images\Lab5\vscode_config_view.png)  
![ssh login with shortcut](Images\Lab5\ssh_shortcut_login.png)  

To test the new login, we can try copying a file to the server without logging in directly.  
1. First create a test file using the touch command in your local terminal.  
2. Now use the scp command with the shorcut for your login.  

![scp on local](Images\Lab5\local_scp_to_server.png)  
This is what the directory on the server looks like **before** the scp:  
![server view before scp](Images\Lab5\remote_before_scp.png)  
This is what the directory on the server looks like **after** the scp:  
![server view after scp](Images\Lab5\server_after_scp.png)  

## Setup Github Access from ieng6  
1. To setup Github access, login to your server account.  
2. Create a .ssh folder in the home directory if it is not already there.
    - Use the command `mkdir .ssh`
3. Then make a new public and private key using this [tutorial](https://trinityxortiz.github.io/cse15l-lab-reports/lab-report-1-week-2.html) except instead of using `-t ed255519` use `-t rsa` and stop after creating the key.  
![keygen server ](Images\Lab5\server_keygen.png)
4. Go to the .ssh directory, and copy the contents the id_rsa.pub file by typing `cat id_rsa.pub` and copying the output.
5. Go to your Github settings and select the 'SSH and GPG Keys' tab.  
![github tab](Images\Lab5\github_settings.png)  
6. Press 'New SSH key'  
![new ssh key](Images\Lab5\new_sshkey.png)  
7. Create a title of your choice. Copy and paste the contents of the public key from earlier and select 'Add SSH key'. 
![](Images\Lab5\add_new_view.png)   
You can now connect to the Github server from your ieng6 account!  
It should look something like this:  
![](Images\Lab5\key_storage.png)  
Your private key should be stored in a file called id_rsa:  
![](Images\Lab5\server_key_location.png)  

Now that we can acces Github from the server, we can run git commands on a repo through the terminal. 
1. Copy the contents from the clone option for SSH in Github.  
![Github SSH clone options](Images\Lab5\git_ssh.png)  
2. Type git clone followed by the copied contents.  
![git clone](Images\Lab5\git_clone.png)  
3. Make a change to the file using the echo command.  
4. Check the git status  
5. Add the file to the staging area using `git add [file]`
6. Commit using `git commit -m "[message]"  
7. Push the [commit](https://github.com/trinityxortiz/cse15l-lab-reports/commit/14b3729d4fb694cfd872402a9049e6605e7115fc) using `git push`   

![git commands](Images\Lab5\commands.png)  

## Copy whole directories with 'scp -r' 
Copying my whole markdown-parse directory to my ieng6 account:  
![recursive scp](Images\Lab5\recursive_scp.png)  

Logging into my ieng6 account after doing this and compiling and running the tests for my repository:  
![login and tests](Images\Lab5\login_after_recursive_copy.png) 

Combining scp, ;, and ssh to copy the whole directory and run the tests in one line.
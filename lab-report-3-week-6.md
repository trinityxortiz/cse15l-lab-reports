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
4. Go to the .ssh directory, and copy the contents the id_rsa.pub file by typing `cat id_rsa.pub`.
5. Go to your Github settings and select the 'SSH and GPG Keys' tab.
6. Press 'New SSH key'
7. Create a title of your choice.
8. Copy and paste the contents of the public key from earlier.  

You can now connect to the Github server from your ieng6 account!


## Copy whole directories with 'scp -r' 

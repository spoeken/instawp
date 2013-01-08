instawp
=======

Install wordpress with a single command, both local and on your development environment, with git offcourse. 
Bootstrap will be downloaded to the themes folder aswell.

How to use it
=============
Remember to have MAMP or whatever you use turned on!

1. Open the script in a text editor and change the creds. 
2. Save the script in your bash scripts folder. Remember to chmod it so its executable. (chmod +x instawp)
3. Open a shell, cd to your localhost directory and type "instawp myprojectname"
4. Spend some time with your coffee cup while the script does your job!

You only have to do step 1 and 2 once :)

How does it do it?
==================
This is a step by step description of what the script does

1.Script is initiated with _instawp myproject_. _myproject_ will be used for folder name and database name 

2. Cd to $LocalPath and create the myproject folder

3. Initiate a bare git repository

4. Cd to hooks and create a post receive hook that checks out all the files.

5. Chmod +x the hook so its executable

6. cd back to the $LocalPath and scp the myproject folder to the server

7. Remove the bare repo to get a clean start

8. Re-initialise git

9. Download the latest wordpress install, unzip it, pull out all the files and delete the folder and the zip file.

10. Create a .gitignore and add wp-config-local.php to it.

11. Commit, add remote server (origin) and push.

12. Create the wp-config file and add credentials for the remote. We allso write some php to check if wp-local-config.php exists. This is all done with sed.

13. Create the wp-local-config and add creds

14. Download twitter bootstrap into wp-content/themes/bootstrap

15. Commit and push to server

16. Create the databases. We use ssh to do this on the server

17. Use curl to initiate the famous wordpress 5 min install both local and on server. More like 1 sec for us though.

18. We are all done :)



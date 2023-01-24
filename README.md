# CTF_BASH_APP_ALLOWLIST_BYPASS

# WARNING: Use at your own risk! No guarantees this is safe!

# Goal:
You hacked into your target, and now need to read secret.txt as a non-root user!
      Your goal is to get secret.txt printed without getting an alert in
      log.txt WHILE chksecure.sh is running! You must first run chksecure.sh (as a non-root user)
      (to simulate an integrity checker-you can't modify this file for this CTF :0)
      (pretend chksecure.sh can't be written to haha)

 Hint: Time is key!

# Setup/Warnings: 
       1. Open a root shell
       2. then run setup.sh to set the proper file permissions and sudo permissions for the unprivileged user for this CTF.
       3. Make sure you use an unprivileged user for this CTF! 
       4. When done, remember to run "visudo" as a root user and delete a line like to not leave a potential vuln in your system!:
             ctf_user ALL = (root) NOPASSWD: /home/ctf_user/ctf/chksecure.sh
         
# Files:
       -setup.sh: set file perms. Do this first and run as root when doing it!

       -chksecure.sh: a security program to check the integrity of 
        do_task.sh and print a potential secret if the contents of
        file.txt is 2. Do not get yourself alerted in log.txt!

       -do_task.sh: ran by chksecure.sh to put a 1 into file.txt (like a lock). Dev forgot something here....

       =secret.txt: the goal is to read this file!

       -log.txt: security log! check this for if you got alerted on!

       -file.txt: kinda like a lock file :)

       -restart/ directory of a backup copy of the files in case you want to reset the files to their original. You may need to reset the file permissions with setup.sh

 Hint 2: Open 2 terminals. 1 to run chksecure.sh, and another to test stuff
Hint 3: You may be modifying files for this task. You may need to run
        cp restart/* /my/ctf/folder
        to reset the files

# Terminal-Basic-Command-Line
Notes on basic command line for Terminal. 
Apple MacOS offers native Terminal app that features access to the command-line interface. Many Mac terminal commands are similar to Linux commands. 

Terminal_Linux Command Line Codes: Type of command, its code, function of the code and examples attached herewith. 

1. **Current Directory or Present working directory**: pwd 
- Function of the code: If you want to find out which directory you are in.
- Example. pwd
- Result: in my case "/Users/dg663"

2. **Change Directory**: cd
- Function of the code: The cd command will change the directory you’re currently working within Terminal to execute other commands on a different directory.
- Example: cd “path/to/directory/”
- Like: cd Desktop
- Result: Changed to Desktop directory

3. **Listing Directory**: ls
- Function of the code: Use ls command after navigating into a directory using the cd command to view the contents inside of the current directory. 
- Example: ls and get everthing inside that directory.
- Also, Use the argument -l command with ls to get even more information about each of the files.
- Example:  ls -l

4. **Open Files**: open 
- Function of the code: When browsing a directory, you may encounter a file that you wish to open on your Mac. That’s where the open command comes in. 
- Example: open “filename”
- i.e. like open Dinesh     
- Then a folder named Dinesh will open up in the new desktop window. 

5. **Copy a file to another directory**: cp
- Function of the code: The cp command facilitates copying a file from one location to another or making a copy of the same file with a new name. 
- Example: cp “filename” “newfilename with directory”
- i.e.  cp  Disease.docx  /Users/dg663/Documents/Disease.docx 
- By doing so, I copied that file named Disease.docx into documents folder.

8. **Move a file**: mv
- Function of the code: When you don’t want to copy a file, but instead move it, use the same format of the cp command, but instead replace cp with mv.
- Example: mv “filename” “path/to/new/file/location”
- i.e.  mv Disease.docx /Users/dg663 (moved to dg663 folder)

9. **Create a text file**: touch
- Function of the code: The touch command allows you to create any type of file, but it’s blank. 
- After you create the blank file, you can open it in a text editor by typing open [filename].
- Example: touch myfile.txt , also you can create other types(doc, csv) by typing touch myfile.doc or touch myfile.csv
- Then open myfile.txt   to open it. 

10. **Create a directory or folder**: mkdir
- Function of the code: The mkdir command will allow you to create a directory (folder) from within the CLI. 
- When you need a place to store new files, just use this command to add a new directory in the current working directory, or specify a full path to the location where you want the new directory to be placed.
- Example: mkdir “path/to/new/directory”
- i.e. mkdir /Users/dg663/new so here a new folder created inside dg663

11. **Rename folder**: mv 
- Function of the code: When you’ve created a folder that has the wrong name, you can easily use the mv command to rename it.
- Example. mv "oldfilename" "newfilename"
- i.e. mv myfile.txt file.txt

12. **Remove an empty directory**: rmdir
- Function of the code: If you want to remove a directory altogether, use the rmdir command followed by the path to the directory.
- Example: rmdir “path/to/directory”
- i.e rmdir /Users/dg663/new now removes that new folder.

13. **Remove nested directories or folder**: rm -R command
- Function of the code: When you want to remove an entire directory that might contain other directories or files, then the rm -R command is where you will turn. 
- This command is irreversible, unlike deleting files in the Finder and being able to restore them from the Trash. 
- When this command is executed, all files and directories inside of the path you specify will be deleted immediately.
- Example: rm -R “/path/to/root/directory”
- i.e. like mkdir /Users/dg663/test created a test directory or folder
- Then this one removes it.  rm -R /Users/dg663/test

*Note: Here rmdir removes only empty directory but rm -R removes both empty and non empty*

12. **Execute commands with superuser privileges**: sudo command
- Function of the code: sudo which stands for "superuser do" is a command that allows a permitted user to execute a command as the superuser or another user.
  i.e. Allows you to access your user privileges while executing the command to administrator privileges. 
- This is required for some commands to run — for instance, removing a file that is owned by another user. 
- When you run this command, you will see a password field appear in Terminal where you will need to type your user account password to finish the command execution.
- Your Mac has security baked in at its core, which is why when typing a password, the command line hides the characters typed for security practices. 
- Remember to never type your password into a field that you did not request!
- Example: sudo “command” i.e like sudo open myfile.txt
- Then, asked for password and you won't know if you have typed or not, it just looks empty. 
- But keep on typing the correct password for your user account. 
- If you are using computer from your school and you don't have full administration control, you might have to allow it manually like by using "self service control" software. 
- You can install it by requesting your IT guys or even you might be able to download on your own. 

13. **List all actively running computer processes**: top
- Function of the code: With top command, you can see the stats of your system updated in Terminal’s window, such as the memory, disk utilization and so on. 
- You’ll also see a running list of the top apps using the CPU, including their state, ports used, memory per app and more, without needing to open the Activity Monitor app on your Mac. 
Example: top 
*Note that: This command will execute until you close Terminal’s window or press Control + C to return execution back to the CLI.*

14. **Quit sub-screen of perpetuity and return to Terminal**: q
- Function of the code: For commands that run in perpetuity when executed, you can end execution of the process by pressing the q key on your keyboard. 
- Alternatively, you can press Control + C.
- Example: q or Ctrl C
*Perpetuity refers to never ending process like top function above*

15. **Clear terminal screen**: clear
- Function of the code: It clear out all commands and returns a clean slate to work from
- Example: clear

16. **Copy contents of a folder to a new folder**: ditto
- Function of the code: The ditto command will execute a copy of all of the contents of one folder into another folder you specify. 
- This is great for when you need to start a new project and use an older project as a base or if you just need to copy files in a folder from your computer to an external drive. 
- Add a -V, as in the example below, to get verbose output for each file copied.
- Example: ditto -V MyFolder MyNewFolder i.e ditto newfolder Dinesh (here newfolder contain a subfolder which was copied to Dinesh using this command)
*Note: You can use -V to get verbose output and you can use it without -V too.* 

17. **Get description of a command**: whatis
- Function of the code: If you are unsure or do not know what some command does, you can use this to get a short description of a command. 
- Example: whatis ditto  then the result will be different things that ditto does. Don't worry about "Not a directory" sign. 

18. **Manual of the command**: man
- Function of the code: If the description is not enough or you want to know more about the command, the good news is that most of the command are shipped with a manual. 
- You can use man command to know more about the command and get a manual of that command. 
- Example: man ditto . The result consists of description with the manual page including but not limited to Name, synopsis, description and so on.

19. **Exit Command**: exit
- Function of the code: It closes the current session in Terminal. Especially used during remote control. 
- If you are directly using in your computer on site, you can just close the window as well. 
- Example: exit
- The result will be saving session.... [Process completed]

20. **Force shutdown apps**: killall 
- Function of the code: If you want to forcefully quit some app, you can use this function. This can be really important sometime. 
- Example: Killall Terminal
- The result is that the terminal window will be closed. 

21. **Github Codes**:
21.1. **Git Clone**: Clone a file or folder 
- Function of the code: If you want to clone a file instead of downloading a zipfile because cloning can help you to keep track of files and can use git push or pull to update the folder. 
- Example: git clone (paste ssh or url)
- The result is that the folder will be downloaded.

21.2. **Cloning the Repository**: To clone the repository, use the following command:
bash
git clone git@github.com:dineshghimire01/REU-Summer-2024-Cornell.git

21.3. **Keeping the Cloned Repository in Sync**
To keep the cloned repository in sync with the original repository, follow these steps:
Fetch the latest changes from the remote repository:
bash
git fetch origin

21.4. **Switch to the main branch**:
bash
git checkout main

21.5. **Pull the latest changes from the remote repository**:
bash
git pull

21.6. **Working on the main Branch**
To work on the main branch and commit your changes, follow these steps:
Check the modified files:
bash
git status

21.7. **Stage the modified files**:
bash
git add <file_name>

Or, to stage all modified files (not recommended):
bash
git add .

21.8. **Commit the changes with a descriptive message**:
bash
git commit -m "Your commit message here"

21.9. **Push the changes to the remote repository**:
bash
git push

or
bash
git push origin

21.10. **Bonus Git Commands**
21.10.1 **Check the status of the current branch:
bash
git status

21.10.2 **View changes made to files**:
bash
git diff

or
bash
git diff <file_name>

21.10.3 **Create a new branch and push it to the remote repository**:
bash
git checkout -b <branch_name>
git push -u origin <branch_name>

21.10.4 **Switch to an existing branch**:
bash
git checkout <branch_name>

21.10.5 **List all branches**:
bash
git branch



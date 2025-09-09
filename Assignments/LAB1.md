# Assignment 1
## Unit 1: Linux Basics
### **```pwd```**: Diplays the full and absolute path of the current working directory.

![alt text](image-10.png)

### **```ls```**: Allows to view all the files and folders in current working directory.

![alt text](<Screenshot 2025-09-09 120953.png>)

### **```ls -a```**: Lists down all file and folder including the one which are hidden.

![alt text](<Screenshot1 2025-09-09 120953.png>)

### **```ls -la```**: Lists all files, including hidden ones, with detailed information.

![alt text](image-9.png)

### **```ls -l linux1.txt```**: Used to list information about files and directories within the file system.

![alt text](image-28.png)

### **```cd scripts```** or **```cd linux```**: Moves into a directory named as scripts/linux.

![alt text](image-11.png)
![alt text](image-14.png)

### **```cd ..```**: Moves the directory back one directory.

![alt text](image-12.png)

### **```mkdir linux```**: Creates a new folder named as linux.

![alt text](image-13.png)

(The directory was changed to linux which proves that linux folder was created.)

### **```touch linux1.txt```** or **```touch linux2.txt```**: Creates a new and empty text file with the specified name.

![alt text](image-17.png)

### **```mv linux1.txt LINUX1.txt```**: Renames the file linux1.txt to LINUX1.txt.

![alt text](image-15.png)

### **```rm linux2.txt```**: It permanently removes the specified file.

![alt text](image-16.png)

### **```nano LINUX1.txt```**: It is a basic termibal based text editor. It opens the specified file and the terminal clears up and Nano editor interface will appear. You will be able to code in the editor.

![alt text](image-4.png)

### **```cat LINUX1.txt```**: Displays the file content in the terminal.

![alt text](image-18.png)

### **```echo "HELLO WORLD!"```**: This command will print the string "HELLO WORLD!" in the terminal.

![alt text](image-19.png)

### **```whoami```**: Used to display the username of the current effective user. This refers to the user account under which the shell or script is currently operating.

![alt text](image-20.png)

### **```man ls```**: It will open the manual page for ls, providing detailed information about its usage, available options and examples.

![alt text](<Screenshot 2025-09-09 172904-1.png>)

### **```grep "Hello" LINUX1.txt```**: It searches for the exact string "Hello" in the file named LINUX1.txt.

![alt text](image-21.png)

### **```chmod u+x linux1.txt```**: It adds execute for owner.

![alt text](image-23.png)

### **```chmod 777 linux2.txt```**: Any user can read, modify and execute linux2.txt.

![alt text](image-25.png)

### **```sudo chown dhr:grp class.txt```**: It is used to change the ownership of a file named as class.txt.

![alt text](image-26.png)

### **```sudo chgrp developers linux1.txt```**: Used to change the group ownership of a file named linux1.txt to a group named "developers".

![alt text](image-27.png)

### **Extra Questions**

Q1. What is the difference between chmod and chown?

Ans. ```chmod:``` 

-This command modifies the permissions of a file or directory. 

-Permissions define what actions such as read, write or execute can be performed by different entities (owner, group, others).

```chown:``` 

-This command modifies the ownership of a file or directory. 

-It changes which user and/or group is associated with the file or directory.

Q2. How do you check current directory and user?

Ans. To check the current directory, we use the command ```pwd```. It displays the full and absolute path of the current working directory.

To check the current user, we use the command ```whoami```. It displays the username of the current effective user.



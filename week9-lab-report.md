# Week 9 - Lab Report 5
## Different ways to use the find command

In lab report 3, I researched different ways to use the grep command. For this lab report, I decided to do the same exploration but with the find command instead.
I found the following commands from <https://www.tecmint.com/35-practical-examples-of-linux-find-command/>

### Find file using name
`find ./directory -name (filename.txt)`
This command is for finding a file by name under a directory. After the "./", replace directory with the directory name and replace "filename.txt" with the exact name of the file.
In this example, we are searching in the directory "written_2" for the file called "Bahamas-History.txt". It returns the path to the file.
![image](https://user-images.githubusercontent.com/122491370/224526835-67857bb8-5eff-412a-a3fb-fe70a72ffd02.png)
In the next example, we `cd` change directory into "travel_guides" first, then search in berlitz2 for the same file.
![image](https://user-images.githubusercontent.com/122491370/224526838-06949de4-0a44-478f-b0e4-17cecae21c4d.png)

### Find directories using name
`find -type d -name (name)`
This command is for finding directories. The `-type d` specifies that we are searching for a directory.
In the first example, we are searching for the directory called "travel_guides".
![image](https://user-images.githubusercontent.com/122491370/224527037-ad8c93de-353e-4750-bfe5-60644cadfd2e.png)
In the second example, we are searching for the directory called "berlitz2".
![image](https://user-images.githubusercontent.com/122491370/224527042-1195021e-4e8c-43be-843f-c706bbd2fa8e.png)

### Find file using name and ignoring case
`find /directory -iname (filename.txt)`
This command is similar to the first command, but it uses `-iname` instead of `-name` to ignore case.
In the first example, 
![image](https://user-images.githubusercontent.com/122491370/224527662-5346102e-f785-4f4a-8a13-1d765fd92dc1.png)
![image](https://user-images.githubusercontent.com/122491370/224527667-6384b810-6d4b-4c80-992b-7746224dfcbd.png)

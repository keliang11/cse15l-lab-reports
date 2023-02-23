# Week 5 - Lab Report 3

## Using the grep command to reverse search a string

`grep -v "string" <file>`

This is one of the commands that I got by asking ChatGPT what are some different ways to use the grep command. I found this one to be the most interesting.

The `-v` option prints a negative result. Instead of printing all the lines in `<file>` that contain "string", it prints all the lines that DON'T contain "string". This command IS case sensitive, which I found out with the two examples below.

In this first example, it prints all the lines in file Bahamas-History.txt that don't contain the string "a". Pretty much every line contains a lowercase "a" except for these two short lines, one of which contain an UPPERcase "A".
![image](https://user-images.githubusercontent.com/122491370/220805424-89490494-f1d9-4f38-8e51-f4dd05696994.png)

In this second example, it prints all the lines in the same file that don't contain the string "A". It printed out many lines that do not contain "A", and a lot of them do contain the lowercase "a".
![image](https://user-images.githubusercontent.com/122491370/220805571-6263b635-bc0a-49fd-b44e-5c1a09463e9e.png)

## Using the grep command to find the file paths

`grep -r -l "string"`

The '-r' option is the resursive search, which looks for all the files containing the "string" in the current directory and also all the subdirectories.

The first example prints out the paths of the files in written_2 that contain the string "vistas". Notice that this includes files from all the subdirectories within written_2, including results from both bertlitz1 and berlitz2.

![image](https://user-images.githubusercontent.com/122491370/217707706-db3b9266-a3fe-41cf-821d-cc953d9d0641.png)

In the second example, the current working directory is new berlitz2. using the same command, it prints out the names of the files in just berlitz2 that contain "vistas", since there are no subdirectories under berlitz2.

![image](https://user-images.githubusercontent.com/122491370/217707758-fc2749c0-cf16-4f29-8c06-07f5132827ee.png)

## Using the grep comment to find the number of files

`grep -l "string" * | wc -l`

This is a command that I found from StackExchange. It finds the *number of files* in the current working directory that contain a certan string. The first example prints zero because there are no files that are directly under skill-demo1-data which contain the string "Lucayans." 

![image](https://user-images.githubusercontent.com/122491370/217704120-0399b497-5337-41a8-89df-0134689264fb.png)

In the second example, I went into berlitz2 then used the command, which returned 5 files containing "vistas" and one file containing "Lucayans".

![image](https://user-images.githubusercontent.com/122491370/217707506-130328a7-4837-4b37-9b6d-f6993b5b87a4.png)

## Using the grep command to find the number of lines

`grep -r "string" | grep -c '' `

I got this command from asking ChatGPT how to find the number of files, which is actually the wrong command. Instead it answered how to find the *number of lines* that contain the certain string. The first example tells you there are 16 lines containing the string "vistas" in all of written_2.

![image](https://user-images.githubusercontent.com/122491370/217708312-e194cd3e-ddfd-46d1-ab53-9b27ad98e497.png)

The second example tells you there are 6 lines containing the string "vistas" in berlitz2. Note that this is a different result from what we got when using the previous command `grep -l "string" * | wc -l` to find the number of *files*.

![image](https://user-images.githubusercontent.com/122491370/217708475-7d9c57b9-978c-4232-811f-bc7e950e5da1.png)

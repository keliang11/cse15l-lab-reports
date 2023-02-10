## Week 5 - Lab Report 3

# Using the grep command to find the text

`grep "string" <directory>`

This is a command for finding all the intances in all the files in the directory that contain the string and prints out each chunk of *text that contains the string*. The first example finds the intances of the string "Luacayans" in berlitz2 and prints out the paragraphs containing them.

![image](https://user-images.githubusercontent.com/122491370/217715966-06780418-5968-4210-96fe-01c78b816b2b.png)

The second example finds the instances of the string "vistas" in berlitz2 and prints out the paragraphs containing them.
![image](https://user-images.githubusercontent.com/122491370/217716203-7f50395e-f887-4cb0-9d08-3d50b1ccfe34.png)

# Using the grep command to find the file paths

`grep -r -l "string"`

This is a command that returns the *path of the files* in the current working directory that contain the string. The first example prints out the paths of the files in written_2 that contain the string "vistas".

![image](https://user-images.githubusercontent.com/122491370/217707706-db3b9266-a3fe-41cf-821d-cc953d9d0641.png)

The second example prints out the paths of the files in berlitz2 that contain the string "vistas", which in this case is just the file names.

![image](https://user-images.githubusercontent.com/122491370/217707758-fc2749c0-cf16-4f29-8c06-07f5132827ee.png)

# Using the grep comment to find the number of files

`grep -l "string" * | wc -l`

This is a command that I found from StackExchange. It finds the *number of files* in the current working directory that contain a certan string. The first example prints zero because there are no files that are directly under skill-demo1-data which contain the string "Lucayans." 

![image](https://user-images.githubusercontent.com/122491370/217704120-0399b497-5337-41a8-89df-0134689264fb.png)

In the second example, I went into berlitz2 then used the command, which returned 5 files containing "vistas" and one file containing "Lucayans".

![image](https://user-images.githubusercontent.com/122491370/217707506-130328a7-4837-4b37-9b6d-f6993b5b87a4.png)

# Using the grep command to find the number of lines

`grep -r "string" | grep -c '' `

I got this command from asking ChatGPT how to find the number of files, which is actually the wrong command. Instead it answered how to find the *number of lines* that contain the certain string. The first example tells you there are 16 lines containing the string "vistas" in all of written_2.

![image](https://user-images.githubusercontent.com/122491370/217708312-e194cd3e-ddfd-46d1-ab53-9b27ad98e497.png)

The second example tells you there are 6 lines containing the string "vistas" in berlitz2. Note that this is a different result from what we got when using the previous command `grep -l "string" * | wc -l` to find the number of *files*.

![image](https://user-images.githubusercontent.com/122491370/217708475-7d9c57b9-978c-4232-811f-bc7e950e5da1.png)

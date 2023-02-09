## Week 5 - Lab Report 3

# Using the grep command to find the text

`grep "string" <directory>`

![image](https://user-images.githubusercontent.com/122491370/217715966-06780418-5968-4210-96fe-01c78b816b2b.png)
![image](https://user-images.githubusercontent.com/122491370/217716203-7f50395e-f887-4cb0-9d08-3d50b1ccfe34.png)

# Using the grep command to find the file paths

`grep -r -l "string"`
Returns the path of the files that contain the string.
![image](https://user-images.githubusercontent.com/122491370/217707706-db3b9266-a3fe-41cf-821d-cc953d9d0641.png)
![image](https://user-images.githubusercontent.com/122491370/217707758-fc2749c0-cf16-4f29-8c06-07f5132827ee.png)

# Using the grep comment to find the number of files

`grep -l "string" * | wc -l`
Find the number of files in the working directory that contain a certan string.
From StackExchange
![image](https://user-images.githubusercontent.com/122491370/217704120-0399b497-5337-41a8-89df-0134689264fb.png)
![image](https://user-images.githubusercontent.com/122491370/217707506-130328a7-4837-4b37-9b6d-f6993b5b87a4.png)

# Using the grep command to find the number of lines

`grep -r "string" | grep -c '' `
From asking ChatGPT how to find the number of files. Instead it answered how to find the number of lines that contain the certain string.

![image](https://user-images.githubusercontent.com/122491370/217708312-e194cd3e-ddfd-46d1-ab53-9b27ad98e497.png)
![image](https://user-images.githubusercontent.com/122491370/217708475-7d9c57b9-978c-4232-811f-bc7e950e5da1.png)

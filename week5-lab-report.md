## Week 5 - Lab Report 3

`grep "string" written_2/travel_guides/berlitz2/*.txt > Lucayans.txt`

`wc Lucayans.txt`
![image](https://user-images.githubusercontent.com/122491370/217704395-6fbfa4ff-1e2d-4e59-a23e-991141e11b20.png)

`grep -r -l "string"`
![image](https://user-images.githubusercontent.com/122491370/217707706-db3b9266-a3fe-41cf-821d-cc953d9d0641.png)
![image](https://user-images.githubusercontent.com/122491370/217707758-fc2749c0-cf16-4f29-8c06-07f5132827ee.png)


`grep -r "string" | grep -c '' `
From asking ChatGPT how to find the number of files. Instead it answered how to find the number of lines that contain the certain string.

![image](https://user-images.githubusercontent.com/122491370/217708312-e194cd3e-ddfd-46d1-ab53-9b27ad98e497.png)
![image](https://user-images.githubusercontent.com/122491370/217708475-7d9c57b9-978c-4232-811f-bc7e950e5da1.png)



`grep -l "string" * | wc -l`
Find the number of files in the working directory that contain a certan string.
From StackExchange
![image](https://user-images.githubusercontent.com/122491370/217704120-0399b497-5337-41a8-89df-0134689264fb.png)
![image](https://user-images.githubusercontent.com/122491370/217707506-130328a7-4837-4b37-9b6d-f6993b5b87a4.png)


# Week 1 Lab Report
## Intro

Hi! This tutorial is for future CSE 15L students about how to log into a course-specific account on ieng6.

First go to <https://sdacs.ucsd.edu/~icc/index.php> and log in using your username and Student ID. Then, click on the account that starts with cs15lwi23.

![image](https://user-images.githubusercontent.com/122491370/214374370-114317dc-9a8a-440d-8097-9252a5bbae68.png)

Then click on the link to change your password. It will take you to a page where you type in your current password and your new password. Choose "no" for the changing TritonLink password and "yes" for changing course-specific account password. Then, press **enter** instead of clicking "check password".

If your password change was successful, you should see the following page below.(SEE BELOW)

![image](https://user-images.githubusercontent.com/122491370/211930276-07ac89c6-6b8b-4595-8a6c-8cabed45f49a.png)

## Installing Visual Studio Code

Next, install VSCode. I already had this installed previously, but it is pretty straightforward. Go to <https://code.visualstudio.com/> and follow the instructions. This process went smoothly for me so I have nothing much to add here.

After successfully installing, you should be able to open a window like the one below.(SEE BELOW)


![image](https://user-images.githubusercontent.com/122491370/211929750-7e9af6d1-5656-4516-9743-a4e813aea728.png)

## Remotely Connecting

Next, open the terminal in VSCode. Open the command palette using `Ctrl` + `Shift` + `P`, type select default profile and select it. 

![image](https://user-images.githubusercontent.com/122491370/214375099-8ef4b446-93e8-4958-ad14-5f568bdb9387.png)

Select git bash, then click the plus sign to open a new bash terminal. 

![image](https://user-images.githubusercontent.com/122491370/211933762-b61f6390-4f25-48f3-b1cf-5bd468219f2a.png)


In the terminal, type `$ ssh cs15lwi23___@ieng6.ucsd.edu` but fill in the blank line with your letters. You should get the question "are you sure you want to continue connecting", to which you should answer yes. Then it will ask for your password.

**IMPORTANT:** Your password won't be visible when you're typing it, due to security reasons. This stumped me when I was doing this lab, so don't let it fool you. It'll seem like you're not typing anything, but it actually is counting what you type.

![image](https://user-images.githubusercontent.com/122491370/211934829-1440f9cf-b850-463c-8afa-53ace159a6da.png)

After typing your password correctly, you should see the below.


![image](https://user-images.githubusercontent.com/122491370/211955813-b0de0c8b-37f7-421c-bebc-7f3f7763af3d.png)


If you see the image below, followed by a notice, it means you probably typed your password incorrectly like I did the first couple of times. Make sure you type it in one go and hit enter!

![image](https://user-images.githubusercontent.com/122491370/211956187-23d0a756-981c-4908-a081-043b5ac0f761.png)


## Trying Some Commands


Now we can try running some commands such as `pwd`, `ls`, `cd`, etc. Below is an example of some commands I tried. Typing `pwd` prints the working directory, `ls` lists out the files in the current directory, `cd..` moves the directory back one directory.

You can also try to open a group member's directory by typing `ls /home/linux/ieng6/cs15lwi23/cs15lwi23xx` but replace `xx` with the group member's username (of course, it will deny access). When you want to log out of the remote server in your terminal, you can press `Ctrl`+ `D` or just type `exit`, as shown in the second image below.

![image](https://user-images.githubusercontent.com/122491370/211929975-b3516774-4cab-4129-b49b-0d216ee511c2.png)


![image](https://user-images.githubusercontent.com/122491370/211930050-3ae35bea-405b-4d63-8ad9-daf423048f1e.png)

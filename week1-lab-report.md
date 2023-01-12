# Week 1 Lab Report
## Kelsey Liang

Hi! This tutorial is for future CSE 15L students about how to log into a course-specific account on ieng6.

First go to https://sdacs.ucsd.edu/~icc/index.php and log in using your username and PID. Then, click on the account that starts with cs15lwi23.

Then click on the link to change your password. It will take you to a page where you type in your current password and your new password. Choose "no" for the changing TritonLink password and "yes" for changing course-specific account password. Then, press **enter** instead of clicking "check password".

If your password change was successful, you should see the following page below.(SEE BELOW)

![image](https://user-images.githubusercontent.com/122491370/211930276-07ac89c6-6b8b-4595-8a6c-8cabed45f49a.png)

## Installing Visual Studio Code

Next, install VSCode. I already had this instealled previously, but it is pretty straightforward. Go to https://code.visualstudio.com/ and follow the instructions.

After successfully installing, you should be able to open a window like the one below.(SEE BELOW)


![image](https://user-images.githubusercontent.com/122491370/211929750-7e9af6d1-5656-4516-9743-a4e813aea728.png)

## Remotely Conencting

Next, open the terminal in VSCode. Open the command pallete, type select default profile. Select git bash, then click the plus sign to open a new bask terminal. 

![image](https://user-images.githubusercontent.com/122491370/211933762-b61f6390-4f25-48f3-b1cf-5bd468219f2a.png)


In the terminal, type `$ ssh cs15lwi23___@ieng6.ucsd.edu` but fill in the blank line with your letters. You should get the question "are you sure you want to continue connecting", which you should answer yes. Then it will ask for your password.

**IMPORTANT:** Your password won't be visible when you're typing it, due to security reasons. This stumped me when I was doing this lab, so don't let it fool you. It'll seem like you're not typing anything, but it actually is counting what you type.

![image](https://user-images.githubusercontent.com/122491370/211934829-1440f9cf-b850-463c-8afa-53ace159a6da.png)

After typing your password correctly, you should see the below.


![image](https://user-images.githubusercontent.com/122491370/211929927-f2b37e35-0c37-485a-baa7-15355008283a.png)

## Trying Some Commands


Now we can try running some commands such as `pwd`, `ls`, `cd`, etc. Below is an example of some commands I tried. You can also try to open a group member's directory (of course, it will demy access). When you want to log out of the remote server in your terminal, you can press ctrl+D or just type `exit`, as shown in the second image below.

![image](https://user-images.githubusercontent.com/122491370/211929975-b3516774-4cab-4129-b49b-0d216ee511c2.png)


![image](https://user-images.githubusercontent.com/122491370/211930050-3ae35bea-405b-4d63-8ad9-daf423048f1e.png)

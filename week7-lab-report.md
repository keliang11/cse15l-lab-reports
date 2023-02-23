# Week 7 Lab Report

### Delete existing forks

I used `rm -rf lab7` to remove lab7. I used `ls` to list out the current subdirectories and make sure lab7 is not there before logging out.

![image](https://user-images.githubusercontent.com/122491370/220839483-b83e094c-c17a-4b63-b0d4-d9a40d5d675a.png)

### Fork repository

I went to the link <https://github.com/ucsd-cse15l-w23/lab7> which should look like the screenshot below.

![image](https://user-images.githubusercontent.com/122491370/220840340-ecf28832-dc19-4fef-9134-c52b2885b38b.png)

After clicking fork at the top right, it should look like this:

![image](https://user-images.githubusercontent.com/122491370/220840435-4b5dfad6-5acc-488f-9be9-8959aa4bfb86.png)

## Timer Start!

### Log into ieng6

Since I was logged out, I logged back into ieng6 with `ssh cs15lwi23amg@ieng6.ucsd.edu`.

![image](https://user-images.githubusercontent.com/122491370/220840578-941f02ec-8ec3-4e8d-850d-3e8d3d0f8c55.png)

### Clone repository

I cloned my fork of the repository by copying this link from an earlier screenshot:

![image](https://user-images.githubusercontent.com/122491370/220840855-c87d980b-adc1-4c2c-9580-3f5da18bf2d6.png)

I entered the command `git clone` then `Ctrl + v` to paste the link + `<enter>`, and then `cd lab7` + `<enter>` to change into the lab7 directory.

![image](https://user-images.githubusercontent.com/122491370/220841081-5ff42119-93e0-4f21-bae2-def9ba5411cd.png)

### Run tests

Running the tests was a big confusing for me because this had been a reoccuring problem with previous labs. I had been using the Windows commands but it did not work. This time, I tried using Mac commands and they actually worked, which was surprising because my device is Windows. I copy-pasted the following two commands then pressed `<enter>` after each:

`javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`

`java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples`

![image](https://user-images.githubusercontent.com/122491370/220842971-3a18e013-2684-4ffb-99e5-aefb075a83e8.png)

### Edit code file

To edit the code file, I used `nano ListExamples.java`, then pressed the down arrow until I got to line 42 where the bug is. Then I pressed the right arrow 12 times until the cursor is right after "index1", backspace and replace the 1 with a 2, as shown in the following screenshot:

![image](https://user-images.githubusercontent.com/122491370/220846850-a0273566-43d9-4cbb-ba0b-8da161c9376d.png)

Then I pressed `ctrl + o <enter>` to save the change and `ctrl + x` to exit editing.

### Run tests successfully

After editing the code file, I pressed the up arrow three times to automatically get the thrid last command I typed `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` and press `<enter>`.

Then, I pressed the up arrow another three times to get `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples` and press `<enter>` to run the test again. This time the test ran successfully:

![image](https://user-images.githubusercontent.com/122491370/220849325-82c25a69-50cd-4970-bc4a-86afc2685c6f.png)

### Commit and push

To commit and push, I typed `git add ListExamples.java` and press `<enter>`, followed by `git commit -m "Updated"`:

![image](https://user-images.githubusercontent.com/122491370/220849599-92096af9-6ca2-43c9-af44-0b7b03ca833b.png)


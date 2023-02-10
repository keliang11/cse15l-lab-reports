# Week 3 Lab Report

## Part 1 - StringServer

```
import java.io.IOException;
import java.net.URI;
import java.util.List;
import java.util.ArrayList;

class Handler implements URLHandler {

    List<String> strings = new ArrayList<String>();
    int size = 0;

    public String handleRequest(URI url){
    
        if (url.getPath().contains("/add-message")) {
            String[] newString = url.getQuery().split("=");
            strings.add(newString[1]);
            return String.format(String.join("\n", strings));

        }else{
            return "404 Not Found!";
        }
                       
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```
![image](https://user-images.githubusercontent.com/122491370/218005014-65ec020d-5a77-489e-bcfb-5925dbc3c254.png)

The structure of it was based on the NumberServer.java that we did in week 2 lab. For this program, I decided to use a List to keep track of the strings. In the handleRequest method, if the URL path contains `/add-message`, it will take the string that comes after `=` and add it to the List. Then, it will take all the strings and join them by concatenating a new line "\n" after each string. The main method of the StringServer class is the same as NumberServer, where it starts a new server with a port number.

In the below screenshot, this is the first string that is entered after running the program. The string "Hello" is after the = sign so handleRequest just adds that string to the List and prints the List.
![image](https://user-images.githubusercontent.com/122491370/218002674-92a60b1c-2274-48d6-b6e4-27830c40fbae.png)

When you enter the second string "world", it is added to the List after "Hello". The String join method takes the first string, then concatenates a new line, then takes the next string in the List, and prints it out as seen in the below screenshot.
![image](https://user-images.githubusercontent.com/122491370/218002732-770ce4a4-c048-47e5-bdfc-7b2490df8b6f.png)


## Part 2 - Bugs

This bug is from the reversed method in ArrayExamples.java and the tester is testReversed in ArrayTests.java. The purpose of the reverse method is to take an array of integers and return a new array with the elements of the input array in reverse order.

The failure inducing input for test I made is to input a simple array of `{1, 2, 3,}` into the method.

```
@Test
  public void testReversed() {
    int[] input2 = {1, 2, 3};
    assertArrayEquals(new int[]{3, 2, 1 }, 
    ArrayExamples.reversed(input2));
  }
  ```
  
  The test that doesn't induce failure is an empty array.
  
  ```
  @Test
  public void testReversed() {
    int[] input2 = {};
    assertArrayEquals(new int[]{}, 
    ArrayExamples.reversed(input2));
  }
  ```
  
For the failure inducing test, the expected output was `{3, 2, 1}` but the actual output differed at the first index, where the expected was 3 but the actual was 0.
  
![image](https://user-images.githubusercontent.com/122491370/215203632-c0f0438b-dd16-4948-a1f9-706c47b83f3f.png)

The bug was actually very simple. If you look at the code in the for loop and the return statement, the `arr` and `newArray` is actually switched. Below is the bug.

```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
  ```

Below is the code after I fixed the bug.

```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
  ```

The bug caused the elements to be copied from the empty new array into the input array, when it should be the other away around. It also returned the existing array, which now has the wrong elements in it. After the bug fix, the method was able to pass the test.

## Part 3

Mostly everything in lab 2 was new to me, such as building and running a server on a remote computer. I haven't done any of that before. Lab 3 debugging was a bit more familiar to me but it was helpful to break things down into symtoms, bugs, failure-inducing inputs.

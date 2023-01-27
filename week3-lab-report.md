# Week 3 Lab Report

## Part 1 - Simplest Search Engine

In week 2 lab, I created a simple search engine. Below is my code:

```
import java.io.IOException;
import java.net.URI;
import java.util.List;
import java.util.ArrayList;

class Handler implements URLHandler {

    List<String> strings = new ArrayList<String>();

    public String handleRequest(URI url){
    
        if (url.getPath().contains("/add-message")) {
            String[] newString = url.getQuery().split("=");
            strings.add(newString[0]);

            for(int i = 0; i < strings.size(); i++){   
                return String.format(strings.get(i) + "\n"); 
            }
        }
            return "404 Not Found!";
           
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

The structure of it was based on the NumberServer.java that we did in week 2 lab. For this search engine, I decided to use a List to keep track of the strings. In the handleRequest method, if the URL path contains `/add-message`, it will take the string that comes after `=` and add it to the List. Then, it will go through each string in the List and print it out on a new line. The main method of the SearchEngine class is the same as NumberServer, where it starts a new server with a port number.

When I tried to use this program, I ran into some problems that I couldn't figure out, so I was unable to actually run the code. I tried to run the commands `javac Server.java StringServer.java` and `java StringServer` similar to the week 2 lab. It said that StringServer.java was not found.

![image](https://user-images.githubusercontent.com/122491370/215204405-0254c95a-efe9-4fc9-bd12-fd03b50ad752.png)

I checked my files and the repository to make sure it was in wavelet, and I couldn't figure out why it wasn't working.

## Part 2 - Bugs

This bug is from the reversed method in ArrayExamples.java and the tester is testReversed in ArrayTests.java. The purpose of the reverse method is to take an array of integers and return a new array with the elements of the input array in reverse order.

The failure inducing input for test I made is to input a simple array of `{1, 2, 3,}` into the method.

```@Test
  public void testReversed() {
    int[] input2 = {1, 2, 3};
    assertArrayEquals(new int[]{3, 2, 1 }, 
    ArrayExamples.reversed(input2));
  }
  ```
  
  The test that doesn't induce failure is an empty array.
  
  ```@Test
  public void testReversed() {
    int[] input2 = {};
    assertArrayEquals(new int[]{}, 
    ArrayExamples.reversed(input2));
  }
  ```
  
For the failure inducing test, the expected output was `{3, 2, 1}` but the actual output differed at the first index, where the expected was 3 but the actual was 0.
  
![image](https://user-images.githubusercontent.com/122491370/215203632-c0f0438b-dd16-4948-a1f9-706c47b83f3f.png)

The bug was actually very simple. If you look at the code in the for loop and the return statement, the `arr` and `newArray` is actually switched. Below is the bug.

```static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
  ```

Below is the code after I fixed the bug.

```static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
  ```

The bug caused the elements to be copied from the empty new array into the input array, when it should be the other away around. It also returned the existing array, which now has the wrong elements in it. After the bug fix, the method was able to pass the test.

## Part 3

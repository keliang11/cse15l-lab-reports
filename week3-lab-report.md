# Week 3 Lab Report

## Part 1 - Simplest Search Engine

In week 2 lab, I created a simple search engine. Below is my code:

```
import java.io.IOException;
import java.net.URI;
import java.util.List;
import java.util.ArrayList;

class Handler implements URLHandler{
 
    List<String> strings = new ArrayList<String>();

    public String handleRequest(URI url){
    
        if (url.getPath().contains("/add")) {
            String[] newString = url.getQuery().split("=");
            strings.add(newString[0]);
        }
        else if (url.getPath().equals("/search")) {
            String[] substring = url.getQuery().split("=");
            for(int i = 0; i < strings.size(); i++){
                if(strings.get(i).contains(substring[0])){
                    System.out.println(strings.get(i));
                    return String.format(strings.get(i));
                }
            }
        }else{
            return "404 Not Found!";
        }
        return null;        
            
    }
    
}

class SearchEngine {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! 
            Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```

The structure of it was based on the NumberServer.java that we did in week 2 lab. For this search engine, I decided to use a List to keep track of the strings. In the handleRequest method, if the URL path contains `/add`, it will take the string that comes after `=` and add it to the List. If the URL path contains `/search`, it will take the substring that comes after `=`. Then, it will go through the strings in the List and see which strings contain the substring, and return those strings. The main method of the SearchEngine class is the same as NumberServer, where it starts a new server with a port number.

When I tried to use this program, I ran into some problems that I couldn't figure out, so I was unable to actually run the code. I tried to run the commands `javac Server.java SearchEngine.java` and `java SearchEngine` similar to the week 2 lab. It said that SearchEngine.java was not found.

![image](https://user-images.githubusercontent.com/122491370/214958352-e6872169-be1c-4402-bd8e-6ffc7c0c0a84.png)

I checked my files and the repository to make sure it was in wavelet, and I couldn't figure out why it wasn't working.

## Part 2 - Two Bugs

In this part, I will choose 2 of the bugs from different files and show: the failure-inducing input (the code of the test), the symptom (the failing test output), the bug (the code fix needed), and the connection between the symptom and the bug.

### Bug #1

The first bug is from the reversed method in ArrayExmaples.java and the tester is testReversed in ArrayTests.java. The purpose of the reverse method is to take an array of integers and return a new array with the elements of the input array in reverse order.

The test I made is to input a simple array of `{1, 2, 3,}` into the method. The expected output was `{3, 2, 1}` but the actual output differed at the first index, where the expected was 3 but the actual was 0.

![image](https://user-images.githubusercontent.com/122491370/214962522-925800e0-1c20-4121-a92c-68ed79624b14.png)

The bug was actually very simple. If you look at the code in the for loop and the return statement, the `arr` and `newArray` is actually switched.

![image](https://user-images.githubusercontent.com/122491370/214963640-b9d84036-be67-44d5-a7b9-7b7e50068c4f.png)

Here's a screenshot of the code after I fixed the bug.

![image](https://user-images.githubusercontent.com/122491370/214962979-2e752b50-09b8-4245-8265-2690a5972511.png)

The bug caused the elements to be copied from the empty new array into the input array, when it should be the other away around. It also returned the existing array, which now has the wrong elements in it. After the bug fix, the method was able to pass the test.

![image](https://user-images.githubusercontent.com/122491370/214964325-7a730953-bff8-44f8-a19f-208a38b69c6d.png)

### Bug #2

The second bug is from the merge method in ListExamples.java and the tester is testMerge in ListTests.java. This method is supposed to take two sorted lists of strings and return a new list that has all the strings in both lists in sorted order.

For the test, I made two lists and put them in the merge method. The first list has "a" and "c" and the second list has "b" and "d" so the expected output should be "a" "b" "c" "d" in that order.

![image](https://user-images.githubusercontent.com/122491370/214966128-6d2400d5-d199-4c44-a88b-6381830f1a29.png)

However, when I ran the test, it took an unusually long time and the result was an out of memory error. From first look it seemed like it does not take into account the differing lengths of list1 and list2. It was hard to pinpoint exactly what was causing the out of memory error but I guessed it might have something to do with the while loops. I ended up rewriting the code using some of the code that was already there:

If list2 is smaller than list1, it will sort all the elements until list2 has been completely sorted. Then, it will add the remaining elements in list1.

![image](https://user-images.githubusercontent.com/122491370/214973356-25b8a9d0-4a99-4945-850f-eb8c157fa6c8.png)

Vice-versa, if list1 is smaller than list2, it will sort all the elements until list1 has been completely sorted. Then, it will add the remaining elements in list2.

![image](https://user-images.githubusercontent.com/122491370/214973396-af8d7335-10df-42c9-800e-2956ec4e4a12.png)

If list1 and list2 are the same size, it will sort all the elements of one array then see which index is smaller and sort the remaining elements of that array.

![image](https://user-images.githubusercontent.com/122491370/214973478-c5ce7a55-fde9-4417-8703-e62e2bc2357e.png)

I ran the same test and well as a couple of tests with different lengths for both lists and they passed.

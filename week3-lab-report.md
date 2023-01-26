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

# Part 2 - Two Bugs

In this part, I will choose 2 of the bugs from different files and show:

1. The failure-inducing input (the code of the test)
2. The symptom (the failing test output)
3. The bug (the code fix needed)
4. The connection between the symptom and the bug

The first bug is from the reversed method in ArrayExmaples.java and the tester is testReversed in ArrayTests.java.

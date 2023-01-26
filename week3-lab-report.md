# Week 3 Lab Report

## Part 1 - Simplest Search Engine

In week 2 lab, we created a simple search engine. Below is my code:

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

The structure of it was based on the NumberServer.java that we did in week 2 lab. For this search engine, I decided to use an ArrayList to keep track of the strings. In the handleRequest method,

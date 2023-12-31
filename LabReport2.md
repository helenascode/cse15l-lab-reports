Helena Phamova - **CSE 15L Lab Report 2**

---

**PART 1**

This is my code for `StringServer`

```
import java.io.IOException;
import java.net.URI;
import java.util.*;

class Handler implements URLHandler {
    List<String> words = new ArrayList<>();
    String retain = "";
    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            retain = "";
            for(String s : words){
                retain += s;
                retain += "\n";
            }
            return retain;
        }
        else if(url.getPath().contains("/add")){
            System.out.println("Path: " + url.getPath());
            String[] parameters = url.getQuery().split("=");
            if(parameters[0].equals("s")){
                retain = "";
                words.add(parameters[1]);
                for(String s : words){
                    retain += s;
                    retain += "\n";
                }
    
                return retain;
            }
            else{
                return "404 Not Found";
            }
        }
        else if(url.getPath().equals("/clear")){
            retain = "";
            words.removeAll(words);
            return "Array all clear";
        }
        else{
            return "404 Not Found";
        }
    }
}

class StringServer{
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

Screenshots using /add-message

![Image](sc1.png)

![Image](sc2.png)

In these screenshots, the method handleRequest is being called with the relevant argument of /add-messages, and the value of the relevant field can be any string.
The values of the relevant fields of the class change as I modify the URL to display a different message. This process entails the method getting called multiple times and every time the string gets stored and retained in the array list called 'words' through the string variable 'retain'.
The values in the array list change as different messages get entered and the messages get logged by storing the previous value, then using the line break to store the newest value.

---

**PART 2**

![Image](sc3.png)


![Image](sc4.png)


![Image](sc5.png)


![Image](sc6.png)

---

**PART 3**

I have definitely learned more commands over the past couple of weeks and solidified the meaning of each of them and what they stand for. For example for the longest time, I always saw people using cd, but I always forget that it stands for change directory. I also learned that once you remember all the commands by heart, navigating yourself through the terminal/command prompt is certainly more efficient. In addition to that, I learned how to connect to a remote computer with ease, knowing what each step entails.

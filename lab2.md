# Lab Report 2

## Code

```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    String entries = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            if (entries == "") {
                return "Enter a string";
            }
            return entries;
            
        }
        else if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                if (parameters[1].contains("&")) {
                    String[] queryParts = parameters[1].replace("+", " ").split("&");
                    entries += String.format("%s: %s", parameters[2], queryParts[0]);
                    entries += "\n";
                    return entries;

                }
                
            }
        }
        return "404 Not Found!";
        
    }
}

class ChatServer {
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

--- 

## Add Message Examples

![Image](photo1.png)

After entering the URL containing `/add-message`, the method `handleRequest` in the `Handler` class is called.

The only argument passed to this method is the URL. Some fields that I created were `String entries`, which stores all messages added, `String[] parameters`, which ensures that the URL format is correct, and `String[] queryParts`, which splits up the message and the user.

The values of `String[] parameters` and `String[] queryParts` changes entirely for each new message. For this specific request, `parameters[0]` is `"s"`, `parameters[1]` is `"Hello%20CSE15L&user"`, and `parameters[2]` is `"brandonkhor"`. `queryParts[0]` `"Hello CSE15L"` and `queryParts[1]` is `"user"`. The formatted message is added onto `String entries`. For this specific request, "brandonkhor: Hello CSE15L" and a new line is added onto `String entries`, which is an empty String at the moment.

---

![Image](photo2.png)

After entering the URL containing `/add-message`, the method `handleRequest` in the `Handler` class is called.

The only argument passed to this method is the URL. Some fields that I created were `String entries`, which stores all messages added, `String[] parameters`, which ensures that the URL format is correct, and `String[] queryParts`, which splits up the message and the user.

The values of `String[] parameters` and `String[] queryParts` changes entirely for each new message. For this specific request, `parameters[0]` is `"s"`, `parameters[1]` is `"Amazing!&user"`, and `parameters[2]` is `"professor"`. `queryParts[0]` `"Amazing!"` and `queryParts[1]` is `"user"`. The formatted message is added onto `String entries`. For this specific request, "professor: Amazing!" and a new line is added onto `String entries`, which is `"brandonkhor: Hello CSE15L"` at the moment.

---

## `ssh` Key Examples

![Image](ls.png)

Absolute path of private key: `/Users/brandonkhor/.ssh/id_rsa`

Absolute path of public key: `/Users/brandonkhor/.ssh/id_rsa.pub`

Example of terminal interaction without being asked for password:

![Image](nopword.png)

## What I've learned

In week 2, I learned how to connect to a server and allow communication between other computers using `ssh`. We went in-depth on the specific parts of a URL, such as ports and queries, and how to run a server both locally and on a remote computer. Finally, I learned the usage of `curl`, which is like `cat` for URLs.

In week 3, I learned about the process of setting up `ssh` keys for easy access. I learned about the usage of `mkdir` and `scp`, which makes a new directory and securely transfers data between computers, respectively. 

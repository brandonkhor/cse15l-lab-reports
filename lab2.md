# Lab Report 2

## Code

```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    String entries = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Enter a string");
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

The only argument passed to this method is the URL. Some fields that I created were `String entries`, which stores all messages added,
`String[] parameters`, which ensures that the URL format is correct, and `String[] queryParts`, which splits up the message and the user.

The values of `String[] parameters` and `String[] queryParts` changes for each new message. For this specific request, 


![Image](photo2.png)

---

## `ssh` Key Examples

![Image](ls.png)

Absolute path of private key: `/Users/brandonkhor/.ssh/id_rsa`

Absolute path of public key: `/Users/brandonkhor/.ssh/id_rsa.pub`

Example of terminal interaction without being asked for password:

![Image](nopword.png)






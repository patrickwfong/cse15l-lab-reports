# Lab Report 2
Patrick Fong
A14080869

## Part 1
Code:
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    
    ArrayList<String> messages = new ArrayList<String>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            String[] messageString = parameters[1].split("&");
            String message = messageString[0];
            messages.add(parameters[2] + ": " + message + "\n");
            String output = "";
            for (String s : messages) {
                output += s;
            }
            return output;
        } else { return "404 Not Found!"; }
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

# Lab 2 Report
## Part 1
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    int num = 0;
    ArrayList<String> allStrings = new ArrayList<String>();
    String temp = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return temp;
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    allStrings.add(parameters[1]);
                    temp += parameters[1] + "\n";
                    return temp;
                }
            }
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
![Image](/LabReport2Image1.png)
![Image](/LabReport2Image2.png)
1. For the first screenshot, the string `Hello` is added in to the String `temp` using code from lines 15 - 22. The query in the URI matches the parameter. It eventually returns `temp` which includes the String `Hello`. For the second screenshot, it also uses the line 15 - 22 but it adds `how are you` to `temp`. The reason that it displays as it own lines is becuase I used `String.format()` method along with `\n` to make sure each input has its own line.
2. With regards to the values in the method, when a new input is entered, it affects the String that is been inputed which is `parameters[1]`. The String value of `parammeters[1]` is also different depending on the input. URI is different depending on the action that takes place. The URI either ends with `/` or `add-message?s=`. 
3. The values change base on the request because I used an if-else statement to match each request to a specific action. If the URI ends with `\`, it only displays the current contents in `temp`. However, if it adds with `add-messages?s=`, then it would add the input into `temp` and display `temp` after changes were made. 
# Part 2

# Lab Report 2
Nitya Pillai | CSE 15L Thursday 10 am B270
## StringServer
In the screenshotted output below, the ```handleRequest``` method is called in my code. This method takes a parameter of ```URI url```. This parameter is essentially the URL that the user types in. We will preform checks on this URL in the method in order to produce specific outputs on the page. In this case, the argument passed to the method would be the path, '''/add-message?s=hello'''.

![Image](./images/lab2ss2.png)

In my code, I defined a variable ```str``` to hold the string that will be added to and outputted on the page. It is initially initialized as empty. However, by passing ```/add-message?s=hello``` as an argument in the handleRequest method, ```str``` is updated to be ```hello```.

Since the URL containes "/add-message", the first if statement returns true. The path is then split at the equal sign. A String array ```parameters``` is initialized with the string before and after the equal sign. Since the string before the equal sign contains "s", the second element in ```parameters``` (the String the user wants to output) is appended to ```str``` along with a new line. In this case, ```str``` is updated to ```hello``` and this value is returned and outputted on the page.

```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler 
{
    String str = "";

    public String handleRequest(URI url) 
    {
        if (url.getPath().contains("/add-message")) 
        {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) 
            {
                str += parameters[1] + "\n";
                return str;
            } 
        }
        
        return "404 Not Found!";
        
    }    
}
```

It is also important to note that variables are also updated in the main method of the StringServer class. The main method takes a command line argument that is used as the port number for the server. Then, the server is started and a new Handler object is created in the process which allows different URL request to be made based on the method specified above.

```
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

In the second screenshotted output below, the user adds another message after their previous one. This once again calls the ```handleRequest(URI url)``` method in the Handler class. This time, ```str``` already holds a value from the previous input ```hello```. Since "/add-message" is part of the URL passed into the method ```/add-message?s=How are you``` and the path has the appropriate formatting with "s=", the ```How are you``` is appended to ```str```. The updated value of ``str``` is returned and outputted to the page as seen below.

![Image](./images/lab2ss1.png)

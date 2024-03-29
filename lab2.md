# **Lab 2** 
## **Part 1**
![Image](chatServer.png)
This is a picture of the code for my `ChatServer`. There are multiple methods in my code that are called when I add a message, such as `getPath()`, `getQuery()`, `split()`, and the method that actually takes in the url `handleRequest()`. `The handleRequest()` has a argument and that is the url itself. The `getPath()` and `getQuery()` methods don’t have any arguments, but they require a url to be able to work on. The `split()` method requires a string argument because that string dictates where the longer string will be split. I created three loccal variables in this class - a `name` string, a `message` string, and a `finalString` string. The `name` string gets updated to the user that's passed in when `/add-message` is run, and the `message` string gets updated to the message that is passed in when `/add-message` is run. The `finalString` string concatenates the `<user> : <message>` string everytime the `/add-message` method is run.

![Image](add1.png)
This is one instance of me using `/add-message`.

![Image](add2.png)
This is another instance of me using `/add-message`.


## **Part 2**
![Image](abspath.png)

This is the absoulute path to the public key.

![Image](privabs.png)

This is the absolute path to the private key.

![Image](loginnopass.png)
This in an instance of me logging into my `ieng6` account in the terminal **without** being asked for my password.

## **Part 3**
There were many new things that I learned about/learned how to do during the past two weeks in lab. One new thing that stood out the most to me was making changes to a website/webpage in real time. We learned how to take in a url in java and use it to modify things that showed up on our website. In addition, we learned a couple of new commands, such as `scp` and `mkdir`. The `scp` command allowed us to securely copy and transfer files/directories from one place to another. The `mkdir` command does what it sounds like - it makes a new directory.

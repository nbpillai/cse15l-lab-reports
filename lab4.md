# Lab Report 4
Nitya Pillai | CSE 15L Thursday 10 am B270

## 1. Setup Delete any existing forks of the repository you have on your account
Since I already had my forked repository cloned onto my account, I have to delete it first. Run the command ```rm -rf lab7``` to delete the existing fork of the repository. This will recursively delete all files in lab7 and thus the entire repository from the remote account.

I will also need to delete my forked repository from before so that I am able to fork it again. To do this, I click the settings button in the top menu bar. 

<img width="1385" alt="Screen Shot 2023-02-23 at 11 37 35 AM" src="https://user-images.githubusercontent.com/40529489/221012200-09bbc83d-d5a8-48a3-b439-f16a9643af1d.png">

Then, scroll all the way down to the "Danger Zone" section. Click delete repository and retype the repository name when prompted to confirm this. 

<img width="929" alt="Screen Shot 2023-02-23 at 11 38 40 AM" src="https://user-images.githubusercontent.com/40529489/221012399-4f96db07-1016-4089-af7e-d6d65e63ec8b.png">

## 2. Setup Fork the repository
Now, to fork the repository visit [the lab 7 repository](https://github.com/ucsd-cse15l-w23/lab7). As shown below, click the fork button in the top right corner. 

<img width="894" alt="Screen Shot 2023-02-23 at 11 33 05 AM" src="https://user-images.githubusercontent.com/40529489/221011363-21d06978-9bd0-45b3-82fd-57dce302cadb.png">

You will be taken to the screen below. Confirm the repository is being forked into your account (your username should show up where "nbpillai" is in the example below. Click "create fork."

<img width="811" alt="Screen Shot 2023-02-23 at 11 40 25 AM" src="https://user-images.githubusercontent.com/40529489/221012760-dbd11016-abfa-41af-bc92-fb1b9913b8f8.png">


## 3. The real deal Start the timer!
## 4. Log into ieng6
Run the command ```ssh cs15lwi23zz@ieng6.ucsd.edu```, replacing zz with your account id. You should now be logged into the remote server.

## 5. Clone your fork of the repository from your Github account
Click the "code" button on your forked repository. Then switch to the SSH tab within this popup and copy the URL.

<img width="1367" alt="Screen Shot 2023-02-23 at 11 43 24 AM" src="https://user-images.githubusercontent.com/40529489/221013349-52e2f9d2-f47d-4e53-89b1-c210f549bf6f.png">

Go back to your terminal and run the command ```git clone <URL you just copied>```

## 6. Run the tests, demonstrating that they fail
Since my previous test runs were very far back in the bash, I will run the command directly. 

To compile tester file run ```javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java```

To run the tester file run ```java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples```

This will result in 1 error. The current code does not pass the second test which tests the merge method. The error will state that there was a timeout error; this means that the program was taking too long to run. In this case, this could indicate that there was an infinite loop.  

## 7. Edit the code file to fix the failing test
By looking at the code in ListExamples.java, we can see that there is a problem in the third while loop in the ```merge``` method. The while loop continues 
as long as ```index2 < list2.size()```. However, within the body of the loop we are incrementing index1. This means that ```index2 < list2.size()``` is always going to return true since it ```index2``` is initially set to 0. To fix this issue, we can change ```index1 += 1;``` on line 43 to ```index2 += 1;``` Now, index2 is being incremented each iteration of the while loop, so this will not be an infinite loop.

To do this using command line, open a new nano window to edit the code file by running the command ```nano ListExamples.java```. This will pop up a nano editor that displays the content of the file and allows you to edit it.

TALK ABT NANO COMMANDS HERE

After making these edits. Press ```<ctrl><o><enter>``` to save changes. Then, exit the nano window by pressing ```<ctrl><x><enter>```

## 8. Run the tests, demonstrating that they now succeed
Since I ran the test commands previously, I can use the up arrow to get my previous commands rather than typing them all out.

To compile, I ran the command 

To run the tests, I ran the command 

All tests should now pass. 

## 9. Commit and push the resulting change to your Github account
First, we have to add the changes that we made. Run the command ```git add ListExamples.java```.

Then we commit the changes with a message. Run the command ```git commit -m "<commit message>"```

Finally, we push our changes using the command ```git push```

You should now be able to see these changes updateed in your forked repository.

# Lab 4 Report
## Log into ieng6
![Image](/LabReport4Image1.png)
1. Enter `ssh cs15lwi23___@ieng6.ucsd.edu`
2. Because I set up `ssh` keys for ieng6, I pressed `<enter>` and I am logged in without the need of the password

## Clone your fork of the repository from your Github account
![Image](/LabReport4Image2.png)
1. Go to the fork of the repository
2. Click on `<> Code`
3. Copy and past the SSH link to the clipboard
4. Type `git clone` in the terminal and paste the SSH link afterwards
5. Click `<enter>`
6. A clone of the repository would be copied to the remote machine (ieng6)

## Run the tests, demonstrating that they fail
![Image](/LabReport4Image3.png)
1. In the terminal, you can do `javac` and `java` to test the file
2. Type `ls` to check if you are in the directory of the cloned repository
3. If not, type `cd lab7` to change into the right directory
4. Type `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`
5. Type `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`
6. The test would be ran and there would be one error

## Edit the code file to fix the failing test
![Image](/LabReport4Image4.png)
1. You can type `nano ListExamples.java` to open up the file in the terminal 
2. You can use arrow keys on your keyboard to move around in the file 
3. The error in the file is the following code:
```
 while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index1 += 1;
    }
```
4. This chunck of code forces the test to run on forever basically `index` would never be greater than the `list2.size` since it is not incrementing
5. Therefore, you have to change the `index` in the while loop into `index2`, therefore fixing the code
6. Press `<down>` arrow key 42 times to go down to the line that is making the mistake. Then you press the `<right>` arrow key 12 times and press `<delete>` 6 times. Now you have deleted `index`, you replace it by type `index2` as the new variable in its place. Now line 43 in the file should show up as `index2 += 1;`.
7. To save the code, you have to do `^O` and press `<enter>` 
8. To exit the editor, you have to do `^X`

## Run the tests, demonstrating that they now succeed
![Image](/LabReport4Image5.png)
1. Type `ls` to check if you are in the directory of the cloned repository
2. If not, type `cd lab7` to change into the right directory
3. Type `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`
4. Type `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`
5. The test would be ran and it should pass

## Commit and push the resulting change to your Github account 
![Image](/LabReport4Image6A.png)
![Image](/LabReport4Image6B.png)
1. To commit `ListExamples.java` into the repository on GitHub, you have to do `git add ListExamples.java` to make sure it is ready to be committed to GitHub
2. Then, you can do `git status` to make sure that `ListExamples.java` is ready to be committed
3. Think of `git status` is like checking the boxes on GitHub to select the files that you want to upload 
4. Then, you can do `git commit -m "with a message of your choosing"` and then `ListExamples.java` is now committed with the new changes and you can see there are bunch of information regarding like its edits
5. Finally, you got to do `git push` which actually updates the file in the GitHub repository
